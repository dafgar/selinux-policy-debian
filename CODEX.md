# Codex Aims

- Keep local SELinux fixes systematic and reviewable, not `audit2allow` output dressed up as policy.
- Prefer dedicated local types, interfaces, and transitions over broad access to generic labels.
- Focus first on smooth boot, login, and core workstation operation for the documented Debian `mcs` setup.
- Preserve the intended role model:
  - ordinary users in `staff_u` with daily work in `staff_r`
  - `sysadm_r` only for explicit elevation
  - `secadm_u` reserved for SELinux administration
- Treat early boot, initramfs handoff, and pre-rootfs policy behavior as first-class constraints.
- Keep local modules isolated under `policy/modules/local` and suitable for frequent rebuild/load cycles.
- Reuse existing base-policy interfaces where they express the right model; add local policy only where the base policy is missing or mismatched for this system.
- Use `dontaudit` only for access that is understood, intentionally denied, and operationally noisy.
- Avoid weakening confinement to silence warnings; prefer fixing labeling, runtime types, and domain boundaries first.
