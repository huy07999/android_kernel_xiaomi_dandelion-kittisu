# KittiSU integration

This tree integrates KittiSU as a Git submodule and uses its manual-hook mode
for the Linux 4.9 kernel.

The integration includes the required hooks for `execve`, `faccessat`,
`stat`/`fstat`, and `reboot`, plus the SELinux symbol visibility changes needed
by old kernels. Production ARM and ARM64 defconfigs for dandelion, angelica,
angelican, angelicain, and cattail enable KittiSU manual-hook mode.

Use the **Build KittiSU kernel** GitHub Actions workflow to build an ARM64
`Image.gz-dtb`. Select the matching device codename when starting the workflow.

The workflow artifact is a raw kernel image, not a flashable boot image. Back up
the stock boot image and package or repack the kernel for the exact installed
firmware before flashing it.
