Custom Trees
============

Navigator
---------
[Creating roomservice.xml](#creating-roomservice-xml)

Creating roomservice.xml
------------------------
Here's a roomservice.xml:

<p>
<?xml version="1.0" encoding="UTF-8"?>
<manifest> 

    <remote name="gh" fetch="git://github.com/" />

    <project name="CyanogenMod/android_device_oneplus_bacon" path="device/oneplus/bacon" remote="gh" />
    <project name="CyanogenMod/android_device_qcom_common" path="device/qcom/common" remote="gh" />
    <project name="CyanogenMod/android_device_oppo_msm8974-common" path="device/oppo/msm8974-common" remote="gh" />
    <project name="CyanogenMod/android_device_oppo_common" path="device/oppo/common" remote="gh" revision="cm-12.0" />
    <project name="CyanogenMod/android_kernel_oneplus_msm8974" path="kernel/oneplus/msm8974" remote="gh" />
    <project name="TheMuppets/proprietary_vendor_oppo" path="vendor/oppo" remote="gh" />
    <project name="TheMuppets/proprietary_vendor_oneplus" path="vendor/oneplus" remote="gh" />
    <project name="CyanogenMod/android_frameworks_opt_connectivity" path="frameworks/opt/connectivity" remote="gh" revision="cm-11.0" />

    <remove-project name="CyanogenMod/android_vendor_cm" />
    <remove-project name="CyanogenMod/android_build" />
    <remove-project name="CyanogenMod/android_art" />
    <remove-project name="CyanogenMod/android_frameworks_av" />
    <remove-project name="CyanogenMod/android_frameworks_base" />
    <remove-project name="CyanogenMod/android_external_sqlite" />
    <remove-project name="CyanogenMod/android_external_bluetooth_bluedroid" />

    <project path="build" name="jgcaap/android_build" remote="gh" revision="new5" />
    <project path="art" name="jgcaap/android_art" remote="gh" revision="new"  />
    <project path="external/bluetooth/bluedroid" name="jgcaap/android_external_bluetooth_bluedroid" remote="github" revision="new" />
    <project path="external/sqlite" name="jgcaap/SQL" remote="gh" revision="new" />
    <project path="frameworks/av" name="jgcaap/android_frameworks_av" remote="gh" revision="new" />
    <project path="frameworks/base" name="jgcaap/android_frameworks_base" remote="gh" revision="new5" />
    <project path="vendor/cm" name="jgcaap/CM_Vendor" remote="gh" revision="new" />
</manifest>
</p>

roomservice.xml starts with `<?xml version="1.0" encoding="UTF-8"?>` like any other xml files.

Than `<manifest>` is required to make it a manifest file.

After that, it is all `<remote>`, than there will be arguments, here's a list of common arguments:

Argument|Usage
--------|-----
name|Remote name
fetch|Git server
review|Review server
revision|Branches or revision

Than, it is all `<project>`, than there will be arguments, here's a list of common arguments:

Argument|Usage
--------|-----
name|Project name
path|Sync to path
remote|Use remote

Some devices need repo replacements, so we have to first remove them, use `<remove-project>`:

Argument|Usage
--------|-----
name|Project name

You can than use `<project>` to sync the replacements. Than end the roomservice with `</manifest>`.

Resync time
-----------

Than, a resync will do what you have added with roomservice.

If you have to sync project replacements, just add `--force-sync` when you are resyncing.
