# Changes since latest release

# Changes in 0.4.0

-   Support conditional delete of snapshots

    Through the config variable delete_if, one can set a predicate that must
    evaluate to true in order to delete the extraneous snapshots. This can
    become handy if one doesn't want to delete these snapshots while running
    on battery, because btrfs-cleaner can be quite aggressive.

-   Support snapshotting of nested subvolumes

    To allow nested subvolumes to be snapshot, I created a helper variable
    with the volumes directory separators being replaced with underscores.
    This variable is used in two places:

    -   howmuch_* variables since they don't allow slashes in their names
    -   Snapshot target name to avoid nesting snapshots

-   Fix bash variable conflicts

    To further avoid bash variable conflicts, replace dots and dashes with
    underscores in addition to slashes.

# Changes in 0.3.0

-   Support FSNAP_CONFDIR as environment variable

    This way, several different configuration directories can be used.

# Changes in 0.2.0

-   Complete overhaul of initial code

    The script now supports multiple configuration files, residing in
    /etc/fsnap. Every subvolume can now be assigned a number of snapshots to
    keep.

# Changes in 0.1.0

Initial release.
