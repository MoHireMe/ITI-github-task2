"# ITI-github-task2"

```sh
 git branch -d branch-name # local branch delete

 git push origin --delete branch-name # remote branch delete
```

## 🏷️ Annotated Tags — The Professional Way

```bash
git tag -a v1.7 -m "Release 1.7"
```

- Stored as full Git objects
- Includes metadata (tagger name, email, date, message)
- Can be **signed** with GPG (`-s`)
- Best for **releases**, **production deployments**, and **auditing**
- Visible in `git show v1.7`
  > Think of this like a full release note stamped in Git history.

---

## 🪶 Lightweight Tags — The Quick & Dirty Shortcut

```bash
git tag v1.7
```

- No metadata — just a named pointer to a commit
- Can’t be signed
- Super fast and simple
- Fine for **internal use**, **temporary markers**, or **experiments**

# 🔁 When to Use `git rebase`

`git rebase` is a powerful way to rewrite history for a **cleaner, linear commit log**. Use it when you care about readability, traceability, and avoiding unnecessary merge commits.

---

## ✅ Use `git rebase` When:

### 1. **Updating Your Feature Branch**

```bash
git checkout feature/login
git fetch origin
git rebase origin/main
```

🎯 Keeps history clean by applying your commits _on top of_ the latest `main`.

### 2. **Before Opening a Pull Request**

```bash
git rebase -i HEAD~5
```

✏️ Interactive rebase to squash/fixup/rename commits — ideal for polishing history before sharing.

### 3. **Syncing with Team Without Merge Noise**

Instead of this:

```bash
git merge main
```

Do this:

```bash
git rebase main
```

🧼 Cleaner, avoids extra merge commits in your branch.

---

## ❌ Avoid `rebase` When:

- The branch is **shared or public** already — rewriting history will mess up your teammates.
- You’re not comfortable resolving **rebase conflicts**.
- You don’t need a perfect commit log and just want to get things merged fast.

---

## ⚠️ Rebase vs Merge TL;DR

| Goal                       | Use `rebase` ✅ | Use `merge` 🔀 |
| -------------------------- | --------------- | -------------- |
| Clean, linear history      | ✅ Yes          | ❌ No          |
| Safe for shared branches   | ❌ No           | ✅ Yes         |
| Keeps all commit context   | ⚠️ Partial      | ✅ Full        |
| Easier conflict resolution | ❌ No           | ✅ Yes         |

---

## 💥 Force Push Warning

If you rebased and already pushed the original history:

```bash
git push --force-with-lease
```

🔐 Safer than `--force`, avoids nuking teammates’ work.

---

### 4.How to list tags

```sh
git tag
```

### 5. how to delete tags

```sh
git tag -d v1.7 #locally

git push origin --delete v1.7 #remote
```

### 6. Display img

![Git Logo](https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg)
