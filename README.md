# GreatGroupCoup
## Learning through branches and forks, with multiple contributors to emulate open-source software flow.
## Project Overview

Welcome to **greatgroupcoup**, a structured simulation of a real-world enterprise software development lifecycle. This repository is designed to teach Java concepts ranging from Core basics to Advanced features, while simultaneously enforcing professional Git workflows involving forking, branching, code reviews, and upstream synchronization.

## Architecture & Hierarchy

This project operates on a 3-tier hierarchy to simulate a standard Open Source contribution model or a large-scale corporate team structure.

1. **Repository Owner (Tier 1):** The Senior Architect. Maintains the `main` source of truth.
2. **Group Leaders (Tier 2):** 10 Leaders. They fork the Owner's repo. They act as the "Maintainers" for their specific group. They review code from Members and submit consolidated PRs to the Owner.
3. **Group Members (Tier 3):** 90 Members (9 per Group). They fork their respective Group Leader's repo. They act as "Contributors".

## Workflow Instructions

### For Group Leaders (Tier 2)

**Setup:**
1. Navigate to the Owner's repository.
2. Click **Fork** (top right) to create a copy in your GitHub account.
3. Clone your forked repository to your local machine:
`git clone https://github.com/YOUR_USERNAME/greatgroupcoup.git`
4. Add the Owner's repo as `upstream`:
`git remote add upstream https://github.com/OWNER_USERNAME/greatgroupcoup.git`

**Daily Workflow:**
1. **Sync with Upstream:** Before starting, ensure your main branch is up to date with the Owner.
```bash
git checkout main
git pull upstream main
git push origin main
```
2. **Reviewing PRs:**
* Go to your GitHub repository -> Pull Requests tab.
* Review the code submitted by your Group Members.
* Request changes if the code violates rules or logic is incorrect.
* **Merge** the PR into your main branch only when it is perfect.
3. **Submitting to Owner:**
* Once you have merged contributions from your members, go to the Owner's repository.
* Raise a **Pull Request** from your `main` branch to the Owner's `main` branch.

### For Group Members (Tier 3)

**Setup:**
1. Wait for your Group Leader to fork the repository.
2. Navigate to **Your Group Leader's** repository (NOT the Owner's).
3. Click **Fork** to create a copy in your GitHub account.
4. Clone your fork:
`git clone https://github.com/YOUR_USERNAME/greatgroupcoup.git`
5. Add your Group Leader's repo as `upstream`:
`git remote add upstream https://github.com/LEADER_USERNAME/greatgroupcoup.git`

**Daily Workflow:**
1. **Sync with Leader:**
```bash
git checkout main
git pull upstream main
git push origin main
```
2. **Create a Feature Branch:** Never code in main.
`git checkout -b feature/yourname-taskname`
3. **Code & Commit:**
* Open your specific file.
* Write the code based on the comments provided.
* `git add .`
* `git commit -m "Implement task for [Topic]"`
4. **Push:**
`git push origin feature/yourname-taskname`
5. **Raise PR:**
* Go to **Your Group Leader's** repository.
* You will see a prompt to "Compare & Pull Request".
* Draft the PR with a clear description of what you implemented.

## Governance & Rules

### Git Rules
1. **No Direct Commits to Main:** All code must go through a branch and a PR. Direct commits to `main` result in immediate rejection.
2. **Branch Naming Convention:**
Format: `feature/<student_name>-<concept>`
Example: `feature/rahul-arraylist-impl`
3. **Commit Messages:**
* Use Imperative Mood (e.g., "Add", "Fix", "Update", not "Added").
* Format: `[GroupXX-MemberXX] Brief description of change`.
* Example: `[G01-M02] Implement prime number logic`.

### PR Review Guidelines
* **Code Style:** Indentation must be consistent (4 spaces). Variable names must be descriptive (camelCase).
* **Logic:** Code must handle the specific edge cases mentioned in the file comments.
* **Compilation:** Code must compile without errors.
* **Rejection Criteria:**
* Committing `.class` files (Source code only!).
* Merging unrelated files.
* Ignoring the Edge Cases listed in the comments.

---

## Folder Structure & Tasks

The repository is organized by Group topics. Below is the file structure and the content for every single file.

```text
src/
├── com/
├── greatgroupcoup/
├── group01_basics/
├── group02_controlflow/
├── group03_arrays/
├── group04_encapsulation/
├── group05_polymorphism/
├── group06_exceptions/
├── group07_collections_list/
├── group08_collections_map/
├── group09_streams/
├── group10_concurrency/
```

### Visual Tree Mapping for each Group Leader and Group Member

<img width="835" height="668" alt="2025-12-31 - 10_06_10 - Excalidraw Whiteboard" src="https://github.com/user-attachments/assets/8f9a355f-14e9-4267-8d24-36d0b0d40b9b" />

### Repository Structure
Here is the complete project directory tree for the **greatgroupcoup** repository.

In this structure:
*   **Directories** represent **Group Leaders** (Topics).
*   **Files** represent **Group Members** (Individual Tasks).

```text
greatgroupcoup/
├── .gitignore
├── README.md
└── src/
    └── com/
        └── greatgroupcoup/
            ├── group01_basics/                  <-- GL1: Java Basics
            │   ├── Member1_Primitives.java      <-- GM1
            │   ├── Member2_TypeCasting.java     <-- GM2
            │   ├── Member3_Scope.java           <-- GM3
            │   ├── Member4_Operators.java       <-- GM4
            │   ├── Member5_Ternary.java         <-- GM5
            │   ├── Member6_WrapperClasses.java  <-- GM6
            │   ├── Member7_CharOperations.java  <-- GM7
            │   ├── Member8_FinalKeyword.java    <-- GM8
            │   └── Member9_ScannerInput.java    <-- GM9
            │
            ├── group02_controlflow/             <-- GL2: Control Flow
            │   ├── Member1_IfElse.java
            │   ├── Member2_SwitchCase.java
            │   ├── Member3_ForLoopFactorial.java
            │   ├── Member4_WhileLoopReverse.java
            │   ├── Member5_DoWhileMenu.java
            │   ├── Member6_BreakStatement.java
            │   ├── Member7_ContinueStatement.java
            │   ├── Member8_NestedLoopsPattern.java
            │   └── Member9_FibonacciSeries.java
            │
            ├── group03_arrays/                  <-- GL3: Arrays & Strings
            │   ├── Member1_ArraySum.java
            │   ├── Member2_FindMinMax.java
            │   ├── Member3_ReverseArray.java
            │   ├── Member4_MatrixAddition.java
            │   ├── Member5_StringPalindrome.java
            │   ├── Member6_StringSubstring.java
            │   ├── Member7_StringBuilderUsage.java
            │   ├── Member8_StringPoolVsHeap.java
            │   └── Member9_ArraySorting.java
            │
            ├── group04_encapsulation/           <-- GL4: OOP Basics
            │   ├── Member1_BankAccount.java
            │   ├── Member2_SingleInheritance.java
            │   ├── Member3_MultilevelInheritance.java
            │   ├── Member4_HierarchicalInheritance.java
            │   ├── Member5_SuperKeyword.java
            │   ├── Member6_ThisKeyword.java
            │   ├── Member7_ConstructorOverloading.java
            │   ├── Member8_CopyConstructor.java
            │   └── Member9_StaticVsInstanceBlock.java
            │
            ├── group05_polymorphism/            <-- GL5: OOP Advanced
            │   ├── Member1_MethodOverloading.java
            │   ├── Member2_MethodOverriding.java
            │   ├── Member3_AbstractClassShapes.java
            │   ├── Member4_InterfaceVehicle.java
            │   ├── Member5_MultipleInheritance.java
            │   ├── Member6_UpcastingDowncasting.java
            │   ├── Member7_DefaultInterfaceMethods.java
            │   ├── Member8_StaticInterfaceMethods.java
            │   └── Member9_InstanceOfCheck.java
            │
            ├── group06_exceptions/              <-- GL6: Exception Handling
            │   ├── Member1_TryCatch.java
            │   ├── Member2_MultipleCatchBlocks.java
            │   ├── Member3_FinallyBlock.java
            │   ├── Member4_ThrowKeyword.java
            │   ├── Member5_ThrowsDeclaration.java
            │   ├── Member6_CustomException.java
            │   ├── Member7_CheckedVsUnchecked.java
            │   ├── Member8_TryWithResources.java
            │   └── Member9_NestedTry.java
            │
            ├── group07_collections_list/        <-- GL7: List & Set
            │   ├── Member1_ArrayListBasic.java
            │   ├── Member2_LinkedListOps.java
            │   ├── Member3_VectorVsArrayList.java
            │   ├── Member4_HashSetUnique.java
            │   ├── Member5_TreeSetSorting.java
            │   ├── Member6_LinkedHashSetOrder.java
            │   ├── Member7_ComparableInterface.java
            │   ├── Member8_ComparatorInterface.java
            │   └── Member9_CollectionsUtility.java
            │
            ├── group08_collections_map/         <-- GL8: Map & Generics
            │   ├── Member1_HashMapBasic.java
            │   ├── Member2_LinkedHashMap.java
            │   ├── Member3_TreeMapSorting.java
            │   ├── Member4_HashtableLegacy.java
            │   ├── Member5_IteratingMaps.java
            │   ├── Member6_GenericClass.java
            │   ├── Member7_GenericMethod.java
            │   ├── Member8_Wildcards.java
            │   └── Member9_PropertiesFile.java
            │
            ├── group09_streams/                 <-- GL9: Java 8 Features
            │   ├── Member1_LambdaBasic.java
            │   ├── Member2_PredicateInterface.java
            │   ├── Member3_ConsumerInterface.java
            │   ├── Member4_SupplierInterface.java
            │   ├── Member5_StreamFilter.java
            │   ├── Member6_StreamMap.java
            │   ├── Member7_StreamReduce.java
            │   ├── Member8_MethodReferences.java
            │   └── Member9_OptionalClass.java
            │
            └── group10_concurrency/             <-- GL10: Multithreading
                ├── Member1_ThreadClass.java
                ├── Member2_RunnableInterface.java
                ├── Member3_ThreadPriority.java
                ├── Member4_SyncMethod.java
                ├── Member5_SyncBlock.java
                ├── Member6_WaitNotify.java
                ├── Member7_DeadlockSim.java
                ├── Member8_ExecutorFramework.java
                └── Member9_CallableFuture.java
```


