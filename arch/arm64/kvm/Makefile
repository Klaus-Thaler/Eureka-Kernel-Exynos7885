#
# Makefile for Kernel-based Virtual Machine module
#

ccflags-y += -Iarch/arm64/kvm
CFLAGS_arm.o := -I.
CFLAGS_mmu.o := -I.

KVM=../../../virt/kvm
ARM=../../../arch/arm/kvm

obj-$(CONFIG_KVM_ARM_HOST) += kvm.o
obj-$(CONFIG_KVM_ARM_HOST) += hyp/

kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/kvm_main.o $(KVM)/coalesced_mmio.o $(KVM)/eventfd.o $(KVM)/vfio.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(ARM)/arm.o $(ARM)/mmu.o $(ARM)/mmio.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(ARM)/psci.o $(ARM)/perf.o

kvm-$(CONFIG_KVM_ARM_HOST) += emulate.o inject_fault.o regmap.o
kvm-$(CONFIG_KVM_ARM_HOST) += hyp.o hyp-init.o handle_exit.o
kvm-$(CONFIG_KVM_ARM_HOST) += guest.o debug.o reset.o sys_regs.o sys_regs_generic_v8.o

kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/vgic.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/vgic-v2.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/vgic-v2-emul.o
kvm-$(CONFIG_KVM_ARM_HOST) += vgic-v2-switch.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/vgic-v3.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/vgic-v3-emul.o
kvm-$(CONFIG_KVM_ARM_HOST) += vgic-v3-switch.o
kvm-$(CONFIG_KVM_ARM_HOST) += $(KVM)/arm/arch_timer.o
