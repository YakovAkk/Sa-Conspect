---
title: Valet Key
date: 2026-04-20
tags:
  - module5
  - security
  - patterns
  - access-control
  - canvas-note
cssclasses:
  - canvas-note
---

# Valet Key

> [!note] Overview
> The ==Valet Key pattern== provides clients with a ==time-limited, scope-limited token== that grants direct access to a specific resource — bypassing the application as an intermediary for data transfer. It offloads bandwidth and compute overhead from the application while maintaining tight access controls through expiry and predefined operation limits.

## How It Works

**A Valet Key** is a token that gives temporary access to specific resources. It allows only certain actions, like reading or writing to storage, or uploading and downloading through a web browser. The client uses this token to access a resource for a set time, with clear limits on what they can do. The token becomes invalid after the time is up and can't be used again.

<picture>

The Valet Key pattern eliminates user provisioning overhead — there's no need to create a user, grant permissions, and later remove the user. The token is ==created at runtime==, with strict limits on time and access, so the user can only use it for the intended purpose.

## Five Use Cases

### Minimize Loading and Maximize Performance

Valet Key allows unlocking resources without remote server calls, and it has no limits on the number of keys that can be issued. Additionally, it eliminates the risk of a failure by avoiding data transfer through application code.

### Minimize Operational Cost

A Valet Key can help by providing direct access to stores and queues, which is cost-efficient and reduces the number of network round trips. The pattern also allows the use of fewer compute resources.

### Constant Large Volume Data Uploads

Regular data upload and download, especially when it involves large volumes of information or files.

### Limited Computer Resources

The pattern is used when the application has ==limited accessible compute resources==, either due to hosting constraints or cost considerations. It is especially beneficial when many concurrent data uploads occur, as it frees the application from handling data transfer.

### Data is Stored in a Separate Data Center

When the application must act as a gatekeeper, there may be additional bandwidth charges for transferring data between data centers, across public or private networks between the client and the application, and then between the application and the data store.

## Strengths and Trade-offs

| Strengths | Trade-offs |
|---|---|
| Offloads data transfer from application | Does not support audit tracking notifications |
| Time-limited tokens reduce misuse risk | Cannot control access frequency |
| No per-user provisioning overhead | Cannot limit data volume during operations |
| Reduces compute and bandwidth costs | Unsuitable for data that needs transformation before storage |
| No limit on number of keys issued | Hard to retrofit into systems with inflexible data transfer design |

## When to Use

> [!example] Decision Hints
> - Use Valet Key when clients need to ==upload or download large files== directly to/from storage.
> - Use when the application must avoid being a bottleneck for data transfer.
> - Use when compute resources are limited or cost-sensitive.
> - Avoid when data must be transformed before being stored or sent to the client.
> - Avoid when audit logging or access frequency control is a hard requirement.

> [!warning] Limitations
> The Valet Key pattern does not support audit tracking notifications or control how often the data can be accessed. It also doesn't limit the amount of data, which can be a problem during upload operations. It is unsuitable for systems where data changes are needed before storage or where the current design makes changing data transfer flow difficult.

## Related Notes

- [[Security Patterns]]
- [[Federated Identity]]
- [[Gatekeeper]]
