# IAM Setup in AWS Console

✅ What is IAM in AWS?

> **IAM (Identity and Access Management)** allows you to **securely manage users, groups, roles, and permissions** in your AWS account.
It helps you control **who can access what**, and **what they can do** with your AWS resources.

 🔐 IAM Main Components:

| Component  | Purpose                                                           |
| ---------- | ----------------------------------------------------------------- |
| **User**   | Individual person with login credentials                          |
| **Group**  | Collection of users with shared permissions                       |
| **Policy** | Rules that define access (in JSON format)                         |
| **Role**   | Temporary access, often used for services or cross-account access |


| Task             | Step                                               |
| ---------------- | -------------------------------------------------- |
| Create group     | IAM → User groups → Create                         |
| Create user      | IAM → Users → Add user                             |
| Give permissions | Add user to group or attach policy                 |
| Transfer access  | Copy permissions or group from one user to another |
| Remove access    | Detach policy or delete user                       |

**IAM Setup in AWS Console**

 🧑‍💼 Step 1: Create a Group (with specific permissions)

1. Go to **IAM Console** → **User groups** → `Create group`
2. Give a group name (e.g., `Admins`, `Developers`)
3. Attach permission policies (e.g., `AdministratorAccess`, `AmazonS3FullAccess`)
4. Click **Create group**

 👤 Step 2: Create a User

1. IAM Console → **Users** → `Add user`
2. Username: e.g., `Vishu-user`
3. Access type:
 ✅ AWS Management Console access (for UI login)
 ✅ Programmatic access (for API/CLI)
4. Set password or auto-generate
5. Add the user to the group you created earlier
6. Finish → Save credentials

🔄 Step 3: Transfer Authority to Another User

 **User A (admin)** is leaving, and you want **User B** to get the same authority:
✅ Option 1: Add User B to the same group
If User A is in the `Admins` group:
Go to **Groups** → `Admins` → **Add user** → select **User B**

**Revoke Access from Old User**

After transferring:
1. Remove User A from groups
2. Deactivate or delete User A
 * IAM → Users → Select **User A** → Actions → **Delete**

Example

| Person    | Role                   |
| --------- | ---------------------- |
| **Vishu** | Current admin (User A) |
| **Dhiru** | New admin (User B)     |

➡️ To transfer authority:

* Add **Dhiru** to `AdminGroup` (with `AdministratorAccess`)
* Remove **Vishu** from the group or delete the user




