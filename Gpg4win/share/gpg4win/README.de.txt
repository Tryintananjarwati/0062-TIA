
                  Deutsche README Datei f?r Gpg4win
                  =================================

Dies ist Gpg4win, Version 3.1.15 (2021-01-12).

Inhalt:

     1. Wichtige Hinweise
     2. ?nderungen
     3. Anmerkungen
     4. Versionsgeschichte
     5. Versionsnummern der einzelnen Programmteile
     6. Rechtliche Hinweise


1. Wichtige Hinweise
====================

Hilfe bei der Installation und Benutzung von Gpg4win bietet Ihnen das
Gpg4win-Kompendium. Sie finden es nach der Installation
auf Ihrem System (wo genau, ist abh?ngig von Ihrer Windows-Version)
oder online auf
    https://www.gpg4win.de/documentation-de.html

Bitte lesen Sie den Abschnitt "3. Anmerkungen" dieses READMEs,
bevor Sie Gpg4win nutzen.

Im Kompendium finden Sie weitere Hinweise zur manuellen oder automatischen
Installation.


Systemvoraussetzungen
---------------------

Gpg4win l?uft auf Windows Versionen 7 oder neuer (bis Windows 10).
32- und 64bit-Systeme werden unterst?tzt. Wird mindestens Windows XP verwendet,
k?nnen einige Komponenten von Gpg4win verwendet werden, sie sind allerdings
nicht offiziell unterst?tzt.

Das Outlook-Plugin GpgOL ist kompatibel mit Microsoft Outlook 2010, 2013 und
2016 (sowohl 32 als auch 64bit) und unterst?tzt E-Mail Transport per SMTP/IMAP
und MS Exchange Server (ab Version 2010).

Mit Gpg4win Version 3.1.2 wurde die Unterst?tzung f?r Outlook 2003 und 2007
aus sicherheitsgr?nden entfernt.

(Aktuellste Angaben auf https://www.gpg4win.de/system-requirements-de.html .)



2. ?nderungen
=============

Die integrierten Gpg4win-Komponenten in Version 3.1.15 sind:

    GnuPG:          2.2.27
    Kleopatra:      3.1.15
    GPA:            0.10.0
    GpgOL:          2.4.10
    GpgEX:          1.0.6
    Kompendium DE:  4.0.1
    Compendium EN:  3.0.0


Neu in Gpg4win Version 3.1.15 (2021-01-12)
-----------------------------------------

- GpgOL: Ein kritischer Fehler der seit Gpg4win-3.1.12 existierte
  wurde behoben bei der Auswahl von "Kein Schl?ssel" f?r einen
  Empf?nger konnte es dazu kommen das an beliebige Schl?ssel
  verschl?sselt wurde. (T5223)

- GpgOL: auto-key-retrieve in der GnuPG Konfiguration f?hrt nun
  nicht mehr zu "Keine Daten" Fehlern beim betrachten signierter
  Mails. (T5164)

- GpgOL: Der Fehler "Keine Daten" wird nun besser behandelt und
  zeigt hilfreiche Informationen in der Mail-Ansicht. (T5164)

- GpgOL: Der Name f?r VS-NfD Konformit?t ist nun in der libkleopatrarc
  konfigurierbar.

- Kleopatra: Der Dialog um neue Schl?ssel zu erstellen wurde
  vereinfacht und macht es nun leichter Schl?ssel ohne zus?tzlichen
  Passphrase Schutz zu erstellen. Dies kann mit der Option
  "enforce-passphrase-constraints" in der gpg-agent Konfiguration
  deaktiviert werden. (T5181)

- Kleopatra: Name und Mailaddresse f?r neue Schl?ssel werden nun ?ber
  Active Directory bef?llt wenn diese Information verf?gbar ist.
  (T5181)

- Kleopatra: Das erstellen von S/MIME CSRs zu OpenPGP Smartcards
  wurde weiter verbessert. (T5127)

- Kleopatra: Die Unterst?tzung f?r Tags in Beglaubigungen wurde
  deutlich verbessert und tags werden nun auch ber?cksichtigt wenn
  man Schl?ssel zur Datei-Verschl?sselung ausw?hlt. (T5174)

- Kleopatra: Das ausf?hren mit erh?hten Rechten (als Administrator starten)
  wird nun verhindert um zu vermeiden das die Dateirechte im GnuPG
  Datenordner fehlerhaft gesetzt werden. (T5212)

- Klepoatra: Das setzen der initialen SigG PIN f?r NetKey Karten funktioniert
  nun auch wenn die generelle PIN nicht gesetzt ist. (T5220)

- GnuPG: Es gibt nun eine systemweite Konfigurationsm?glichkeit
  Konfigurationsdateien unter "%ProgramData%\GNU\etc\gnupg" werden
  nun ber?cksichtigt. Das Format entspricht der Nutzerkonfiguration
  unter "%AppData%\gnupg" mit zus?tzlicher Syntax um Optionen zu
  erzwingen und andere zu ignorieren. (T4788)

- GnuPG: OpenPGP Zertifikate k?nnen nun automatisch
  ?ber Active Directory bezogen werden.

- GnuPG: F?r LDAP Schl?sselserver wird nun ein verbessertes
  Schema verwendet.

- GnuPG: Auf Version 2.2.27 aktualisiert:
  https://lists.gnupg.org/pipermail/gnupg-announce/2021q1/000452.html

  Ank?ndigung von Version 2.2.26:
  https://lists.gnupg.org/pipermail/gnupg-announce/2020q4/000451.html

3. Hinweise
===========

- GpgOL

  * Crypto E-Mails, die als Anhang weitergeleitet wurden,
    werden nicht verarbeitet.

  * Integrierte Microsoft spezifische OLE Objekte sind nicht
    unterst?tzt.

  * Als weitere Sprachen sind nur Englisch, Niederl?ndisch
    und Portugiesisch verf?gbar.

- Allgemein

  * F?r Version planen wir mit GpgOL, optional, in einen st?rker
    automatisierten Modus zu wechseln. Dies w?rde die GnuPG-Option
    setzen:

        trust-model tofu+pgp

    Da das neue Vertrauensmodell noch nicht vollst?ndig in Kleopatra behandelt
    wird (insbesondere bez?glich Dateisignaturen), ist diese Option
    nicht voreingestellt.

    Sie k?nnen sie jedoch manuell in der gpg.conf setzen. Das neue
    Vertrauensmodell wird von GpgOL bereits unterst?tzt.


4. Versionsgeschichte
=====================

Eine aktuelle, deutschsprachige ?bersicht der ?nderungen finden Sie online
unter: https://www.gpg4win.de/change-history-de.html
Im Weiteren finden Sie die Eintr?ge aus der englischen NEWS-Datei:


Noteworthy changes in Version 3.1.15 (2021-01-12)
------------------------------------------------
   * GpgOL: Fixed a critical issue since Gpg4win-3.1.12 where
     the selection of "No Key" for a recipient could lead to arbitrary
     keys selected instead. (T5223)

   * GpgOL: auto-key-retrieve in the GnuPG config now no longer
     leads to "No Data" errors when viewing signed mails. (T5164)

   * GpgOL: The error "No Data" now leads to more useful output in
     the mail view. (T5164)

   * GpgOL: The name for VS-NfD compliance is now configurable through
     libkleopatrarc.

   * Kleopatra: The dialog to create new keys has been simplified and
     makes it easier to create keys without protection. This can
     be disabled by setting "enforce-passphrase-constraints" in the
     gpg-agent configuration. (T5181)

   * Kleopatra: Name and e-mail for new keys are now obtained through
     active directory if they are available. (T5181)

   * Kleopatra: Creating S/MIME CSRs for OpenPGP Smartcards has been
     further improved. (T5127)

   * Kleopatra: Tag support for certifications has been greatly improved
     and is now also available when adding keys in the file encrypt
     dialog. (T5174)

   * Kleopatra: Elevated execution of Kleopatra (run as Administrator)
     is now prevented to avoid accidental permission problems in the
     GnuPG data folder. (T5212)

   * Kleopatra: Setting the initial SigG PIN for NetKey cards now also
     works if the generic PIN is not set. (T5220)

   * GnuPG: Now supports system wide configuration files in
     "%ProgramData%\GNU\etc\gnupg" so Administrators can both set defaults
     and enforce a specific configuration. The Format is the same as
     the user configuration under "%AppData%\gnupg" with additional syntax
     to enforce some options and ignore other options. (T4788)

   * GnuPG: OpenPGP certificates can no be obtained automatically
     over Active Directory.

   * GnuPG: The scheme for LDAP access has been improved.

   * GnuPG: Updated to 2.2.27 See:
     https://lists.gnupg.org/pipermail/gnupg-announce/2021q1/000452.html

     Announcement for 2.2.26:
     https://lists.gnupg.org/pipermail/gnupg-announce/2020q4/000451.html

~~~~~~~~~~~~~~~
GnuPG:          2.2.27
Kleopatra:      3.1.15
GPA:            0.10.0
GpgOL:          2.4.10
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.14 (2020-11-25)
------------------------------------------------
   * Kleopatra: It is now possible to revoke certifications with Kleopatra.
     (T5094)

   * Kleopatra / GnuPG: Unicode home directories are now supported.
     (T5055)

   * Kleopatra: Directories for encryption may now contain unicode
     filenames. (T4083)

   * Kleopatra: Improved Smartcard support, preshadowing the full
     multicard support with GnuPG 2.3. (T5066)

   * Pinentry: The dialog should now receive input focus in more scenarios.
     (T4123)

   * GpgOL: Plain text mails without attachments are properly displayed
     again.

   * GpgOL: Plain text e-mails without attachments are displayed correctly
     again.

   * GnuPG: Updated to 2.2.25
    ( https://lists.gnupg.org/pipermail/gnupg-announce/2020q4/000450.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.25
Kleopatra:      3.1.14
GPA:            0.10.0
GpgOL:          2.4.8
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.13 (2020-09-04)
------------------------------------------------

   * GnuPG: Updated to 2.2.23 to fix CVE-2020-25125.
     ( https://lists.gnupg.org/pipermail/gnupg-announce/2020q3/000448.html )

   * GpgOL: Fixed an issue where unencrypted drafts of mails were stored
     on the an Exchange Server and could be restored through the
     "recently deleted items" option. Especially if the draft encryption,
     introduced in Gpg4win-3.1.8, is used this can be a security issue. (T5022)

     Gpg4win cannot offer guarantees that Outlook does not send data which
     is entered *before* the encryption to Microsoft or an Exchange Server.
     Under Windows with Outlook this is impossible to control.
     The draft encryption option is our best effort to avoid this.

~~~~~~~~~~~~~~~
GnuPG:          2.2.23
Kleopatra:      3.1.12
GPA:            0.10.0
GpgOL:          2.4.7
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.1.12 (2020-07-24)
------------------------------------------------

   * GpgOL: Improved handling of mails with encrypted
     subjects. (T4796)

   * GpgOL: Improved integration with Web Key Services to
     automatically provide public keys. (T4839)

   * GpgOL: The addressbook integration is now more visible. (T4874)

   * GpgOL: Group accounts are now properly considered when
     preselecting the signing key. (T4090)

   * GpgOL: During signature verification a preview of the
     content is now displayed. (T4944)

   * GpgOL: Printing of encrypted mails now works correctly
     after changing the printer. (T4890)

   * GpgOL: Security level of keys obtained from a Web Key
     Directory is now properly shown as Level 2.

   * GpgOL: Permanently decrypt now works more reliably and
     should no longer lead to "No Data" errors. (T4718)

   * GpgOL: Long lines in plaintext mails should no longer
     be displayed as multiple lines after decryption. (T4987)

   * GpgOL: Attachments with filenames that are not allowed
     on Windows can now be handled. (T4835)

   * GpgOL: Mails with exactly one attachment and no body
     are now displayed correctly.

   * GnuPG: Symmetric encryption now uses only one
     password dialog. (T4971)

   * GnuPG: Improved certificate import for S/MIME
     certificates. (T4847)

   * GnuPG: Added support for CardOS 5 Smartcards
     based on the D-Trust 3.1 card.

   * GnuPG: Support for rsaPSS signatures has been added. (T4538)

   * GnuPG: The "Quality" of a new passphrase is
     no longer incorrectly displayed. (T2103)

   * Kleopatra: Overwriting secret key exports now works
     correctly. (T4709)

   * Kleopatra: Fixed a case where file sign & encrypt dialogs
     would not be shown on high DPI systems. (T4819)

   * Kleopatra: The sorting of multiple tabs has been
     fixed.

   * Kleopatra: The minimal lenght of the Name has been
     reduced to better support non latin names. (T4745)

   * Kleopatra: The filename suggestion for key exports
     has been improved to avoid confusion between
     public and private key exports. (T4995)

   * Kleopatra: Authentication subkeys can now be exported
     in the OpenSSH format.

   * Kleopatra: Markup is now automatically removed when
     pasting into the notepad. (T4969)

   * Kleopatra: "updating..." as key validity is no
     longer displayed incorrectly when doing a keyserver
     search. (T4948)

   * Gpg4win: The file and URL connections with Kleopatra now properly
     split arguments and potential external data like filenames and
     the search query.
     This prevents a security issue where Kleopatra could be triggered
     to load a library from a filename provided through an unescaped
     URL.

~~~~~~~~~~~~~~~
GnuPG:          2.2.21
Kleopatra:      3.1.12
GPA:            0.10.0
GpgOL:          2.4.6
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.11 (2019-12-17)
------------------------------------------------

   * GpgOL: Improved compatibility with other clients for S/MIME
     e.g. the Outlook web interface. (T4543 T4525)

   * GpgOL: E-Mails which are too large to fully decrypt / verify
     on a Server with E-Mail size limits are now handled with a proper error.
     (T4731)

   * GpgOL / Kleopatra: The GnuPG-System config page can now
     be hidden.

   * GpgOL: There is now an additional configuration option to
     always show the security approval dialog, even with full automation.

   * GpgOL: E-Mails are no longer always classified as HTML.

   * GpgOL: Saving E-Mails as files now also works when the
     mail is opened in its own Window.

   * GpgOL: Fixed a rare case where GpgOL could crash when opening
     a Mail from the file system.

   * GpgOL: The security approval dialog now has additional
     info buttons to show extended information.

   * Kleopatra: The certify dialog has been reworked to be
     more user friendly and require less clicks. (T4649)

   * Kleopatra: New Feature "Search Tags": When certifying a user
     identity you can now add additional "Tags". Tags are shown
     which are made by any user that has full ceritification
     trust. They can be used to group or search keys by additional
     information. (T4734)

   * Kleopatra: There is now an error message when a key could not
     be found during file encryption.

   * Kleopatra: The Smartcard Management now also works for
     OpenPGP 3 cards e.g. newer Yubikeys.

   * GnuPG: Network access is now much faster if IPv6 is
     not available. (T4165)

   * GnuPG: Prepare against chosen-prefix SHA-1 collisions in key
     signatures. This change removes all SHA-1 based key signature
     newer than 2019-01-19 from the web-of-trust.
     Note that this includes all key signature created with DSA-1024 keys.
     The new  option --allow-weak-key-signatues can be used to override
     the new and safer behaviour.  (T4755, CVE-2019-14855)

   * GnuPG: Updated to Version 2.2.19.
     (See: https://gnupg.org for additional News.)

~~~~~~~~~~~~~~~
GnuPG:          2.2.19
Kleopatra:      3.1.11
GPA:            0.10.0
GpgOL:          2.4.4
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.1.10 (2019-07-14)
------------------------------------------------

   * GpgOL: Fixed a possible plaintext leak to the
     mail server, which could occur when opening and closing mails
     while the mail was also visible in the message list. (T4622 T4621)

   * GnuPG: Ignore all key-signatures received from keyservers.  This
     change is required to mitigate a DoS due to keys flooded with
     faked key-signatures.  The old behaviour can be achieved by adding
       keyserver-options no-self-sigs-only,no-import-clean
     to your gpg.conf.  (T4607)
     See: https://wiki.gnupg.org/WKD for an alternative to the
     keyservers.

   * GnuPG: Updated to Version 2.2.17.
     (See: https://gnupg.org for News.)

~~~~~~~~~~~~~~~
GnuPG:          2.2.17
Kleopatra:      3.1.8
GPA:            0.10.0
GpgOL:          2.4.2
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.9 (2019-06-15)
------------------------------------------------

   * Kleopatra: Fixed autocompletion of recipients. (T4569)

funktioniert nun wieder. (T4569)

   * GpgOL: Printing of crypto mails now fully works. (T4560)

   * GpgOL: File -> Save As does now work. (T4318)

~~~~~~~~~~~~~~~
GnuPG:          2.2.16
Kleopatra:      3.1.8
GPA:            0.10.0
GpgOL:          2.4.0
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.8 (2019-06-06)
------------------------------------------------

   * Kleopatra: The certificate view now has configurable columns
     and no longer looses state after a refresh.
     (T4557 T3888 T3604)

   * Kleopatra: The Dialog to add user-ids was improved and simplified.
     (T4139)

   * Kleopatra: A warning has been removed when searching for
     fingerprints and the suggested behavior automated. (T4164)

   * Kleopatra: The user-id certifications view has been improved
     to better show the state of the certifications. (T4458)

   * GpgOL: S/MIME certificates can now be placed similar to OpenPGP
     keys into the address book. (T4479)

   * GpgOL: A possible loss of attachments when forwarding crypto
     and non crypto mails has been fixed. (T4526)

   * GpgOL: It no longer can happen that attachments with a
     Content-ID are hidden even though they are not visible
     in the message body. (T4203)

   * GpgOL: Added Draft encryption as an optional and currently
     experimental feature. (T4388)

   * GpgOL: S/MIME Mails now use the same icons as Outlook to avoid
     user confusion. (T4558)

   * GpgOL: The internal format for S/MIME Messages has
     been changed to improve compatibility with other clients.
     (T4278 T4553)

   * GpgOL: Automatic encryption is no longer triggered for
     users without an S/MIME certificate if S/MIME is preferred.
     (T4483)

   * GpgOL: A possibility that S/MIME Mails were still handled by
     GpgOL even though S/MIME was disabled no longer exists.
     (T3935)

   * GpgOL: The security approval dialog has been improved and
     handles situations with multiple keys better. (T4559)

   * GpgOL: Several rare crashes have been fixed when memory debugging
     was enabled.

   * GpgOL: Now accepts some more broken mails from other clients.
     (T4552)

   * GpgOL, Kleopatra: A race condition that could lead to
     random hang-ups of the complete GnuPG system after
     using S/MIME has been fixed.

   * GnuPG: Updated to Version 2.2.16.
     (See: https://gnupg.org for News.)

~~~~~~~~~~~~~~~
GnuPG:          2.2.16
Kleopatra:      3.1.8
GPA:            0.10.0
GpgOL:          2.4.0
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.1.7 (2019-03-28)
------------------------------------------------

   * Kleopatra: Fixed a regression from 3.1.6 that
     broke secret key export, keyserver refresh and
     keyserver upload. (T4438)

   * GPA: Fixed regressions from 3.1.6 that could
     lead to crashes. (T4440 T4439)

~~~~~~~~~~~~~~~
GnuPG:          2.2.15
Kleopatra:      3.1.7
GPA:            0.10.0
GpgOL:          2.3.3
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.6 (2019-03-27)
------------------------------------------------

   * Kleopatra: An issue has been fixed that could cause
     Kleopatra to generate broken TAR archives. (T4332)
     If you are affected see:
     https://wiki.gnupg.org/TroubleShooting#Restoring_corrupted_Archives_created_by_Kleopatra

   * Kleopatra: When importing from X509 directory services
     trusted-certs from dirmngr are also used. (T4266)

   * Kleopatra: Secret key backup has been simplified.
     (T4089)

   * Kleopatra: It is now possible to generate keys
     without signing capability. (T4373)

   * Kleopatra: Startup time has been slightly
     improved.

   * Kleopatra: Generating keys on OpenPGP Smartcards
     works again. (T4428)

   * Kleopatra: Shows the embedded, encrypted, file name if it
     differs from the actual file name. (T4390)

   * Kleopatra, GnuPG: Can now directly import secret keys exported
     from Symantec PGP Desktop. (T4392)

   * Pinentry: A problem preventing pinentry from starting
     in some minimal installations has been fixed. (T4347)

   * GPA: An error when generating new keys has been fixed.
     (T4265)

   * GpgOL: The context menu of a crypto mail now offers to
     permanently decrypt a message. (T3895)

   * GpgOL: Forwarding sent crypto mails works now. (T4321)

   * GpgOL: S/MIME Mail detection has been improved. Especially
     when sending from exchange to exchange. (T4262 T3935)

   * GpgOL: Now shows diagnostics in case sign/encrypt failed
     (T4435)

   * GpgOL: A crash when memory debugging was enabled
     has been fixed. (T4262)

   * GpgOL: With the new option "Import any keys included in mails"
     GpgOL can now automatically import keys from mail headers
     and attachments. (T4432)

   * GpgOL: The option to automatically toggle secure can now
     be modified to do this even if the keys are untrusted.
     (T4432)

   * GpgOL: An encrypted subject (e.g. from Enigmail) is now
     shown after decryption. (T4433)

   * GpgOL: Now uses descriptive names for OpenPGP MIME parts.
     (T4258)

   * GpgOL: Now provides a minimal API for other
     Addins or Programs to work with
     crypto mails which GpgOL would otherwise lock.
     (T4241)

   * GpgOL: There is now a warning in case GpgOL can't
     represent an Outlook internal attachment format, like
     for an Event. (T4184)

   * GnuPG: An issue that could cause dirmngr not to launch
     on some systems has been fixed. (T3381)

   * GnuPG: Updated to Version 2.2.15.
     (See: https://gnupg.org for News.)

~~~~~~~~~~~~~~~
GnuPG:          2.2.15
Kleopatra:      3.1.6
GPA:            0.10.0
GpgOL:          2.3.3
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.1.5 (2018-11-13)
------------------------------------------------

   * GpgOL: Random misbehavior (crashes, freezes, etc.) after
     working with S/MIME has been fixed. (T4111)

   * GpgOL: It is now possible to create a system wide
     default configuration. (T4204)

   * GpgOL: Fixed encoding problems with unusual charsets.
     (T4156)

   * GpgOL: Disabling data debugging removes more data
     from debug logs. (T4193)

   * GpgOL: The internal access to key data is now faster.
     This fixes issues with automatic key resolution. (T4218)

   * GpgOL: Emails in Junk folders can now be moved and
     are marked. (T4188)

   * GpgOL: The question to save changes no longer appears when
     using the File menu. (T4236)

   * Kleopatra: Random misbehavior (crashes, freezes, etc.) after
     working with S/MIME has been fixed. (T4111)

   * Kleopatra: Improved CRL cache operations. (T3967)

   * GnuPG: Updated to version 2.1.11
     (See: https://lists.gnupg.org/pipermail/gnupg-announce/2018q4/000432.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.11
Kleopatra:      3.1.4
GPA:            0.10.0
GpgOL:          2.3.2
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.4 (2018-10-17)
------------------------------------------------

   * GpgOL: It is now possible to configure OpenPGP keys through
     Outlook contacts. (T4122)

   * GpgOL: For improved security the signers email is now
     shown in the trusted sender category. (T4183)

   * GpgOL: Fixed the error: "Failed to resolve recipients." occurring
     too often. (T4132 T4129)

   * GpgOL: A problem that could prevent mails with Microsoft Office
     files as attachments from beeing secured has been fixed. (T4131)

   * GpgOL: Debugging has been improved and is now configurable in the
     config dialog. (T4120 T4121)

   * GpgOL: It is now possible to generally prefer S/MIME. (T4178)

   * GpgOL: A problem that caused attachments to be hidden in
     unusually structured emails has been fixed. (T4161)

   * GpgOL: A crash when viewing mails in unknown codepages has
     been fixed. (T4141)

   * GpgOL: It is now possible to automatically import X509 certificates
     for S/MIME from configured directory services. (T4174)

   * GpgOL: Various smaller bugfixes.

   * GPA: Search now also queries Web Key Directories.

   * GPA: Improved error handling with diagnostic output.

~~~~~~~~~~~~~~~
GnuPG:          2.2.10
Kleopatra:      3.1.3
GPA:            0.10.0
GpgOL:          2.3.1
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.1.3 (2018-08-31)
------------------------------------------------

   * GpgOL: It is now possible to move crypto mails while they
     are open. (T3459)

   * GpgOL: Messages are automatically secured if certified keys / certificates
     can be found for each recipient.
     This can be turned off with the option "Automatically secure messages".
     (T3999)

   * GpgOL: Support for distribution lists has been added. (T4065)

   * GpgOL: S/MIME can now be preferred when automatically resolving
     recipients. (T3961)

   * GpgOL: Encryption should no longer cause Outlook to freeze.
     (T3838)

   * GpgOL: Mails moved by Outlook folder rules are now handled by
     GpgOL. (T4070)

   * GpgOL: The config dialog was changed to improve future extensibility.
     (T3961)

   * GpgOL: Fixed various memory errors and stability problems.

   * GpgOL: Verifying mails a second time is now much faster.

   * GpgOL: Crashes related to filenames of attachments have been fixed.
     (T4062 T4032)

   * GpgOL: An error has been fixed which could lead to attachments not
     beeing displayed.

   * GpgOL: Sent on behalf of is now respected when verifying a signature.
     (T4110)

   * Kleopatra: Now offers diagnostic information in case of file
     decryption errors.

   * Kleopatra: Support for NetKey v3 Smartcards has been improved.
     (T4080)

   * Kleopatra: Decryption errors caused by missing integrity protection
     (MDC) are now handled properly. (T4038)

   * Kleopatra: Update check can now be disabled more easily. (T4043)

   * Kleopatra: Special characters in GnuPG output should be displayed
     correctly. (T2983)

   * Kleopatra: p7m and p7s files are now also registered to be
     opened with Kleopatra. (T3890)

   * Kleopatra: Various minor improvements. (T3238 T4078 T3229 T4041)

   * Installer: Silent install now correctly closes running Gpg4win
     applications. (T4051)

   * Installer: New optional module "Browser Integration" to register
     GnuPG as backend for Mailvelope 3.0.

   * GnuPG: The dirmngr process no longer requests Windows firewall
     access. (T3610)

   * GnuPG: S/MIME data is now handled faster. (T4069)

   * GnuPG: Updated to 2.2.10
     (See: https://lists.gnupg.org/pipermail/gnupg-announce/2018q3/000428.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.10
Kleopatra:      3.1.3
GPA:            0.9.10
GpgOL:          2.3.0
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.2 (2018-06-17)
------------------------------------------------

   * GpgOL: Removed support for Outlook 2003 and 2007. (T3984)

   * GpgOL: Unsigned S/MIME mails are now treated more restrictive.
     (T3986)

   * GpgOL: Replies to unencrypted no-mime mails no longer only display
     quoted contents. (T3964)

   * GpgOL: Handling of special characters in no-mime mails has been
     improved. (T3975)

   * GpgOL: Added dutch and ukrainian translations.

   * GpgOL: Additional crashes habe been fixed. (T3946)

   * GpgOL: The resolution of ambigous recipients has been improved. (T3978)

   * Kleopatra: Small usability improvements.

   * GnuPG: Update to version 2.2.8 (CVE-2018-0495 CVE-2018-12020)
     (See: https://lists.gnupg.org/pipermail/gnupg-announce/2018q2/000425.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.8
Kleopatra:      3.1.2
GPA:            0.9.10
GpgOL:          2.2.0
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.1 (2018-05-03)
------------------------------------------------

   * General: An issue was fixed, which could lead to
     "Invalid crypto engine" errors. (T3919)

   * S/MIME: An issue was fixed, which could prevent successful CRL
     checks. (T3923)

   * S/MIME: OCSP certificate checks can now be combined with CRL
     checks.

   * S/MIME: Certificate search on LDAP Servers works again. (T3937)

   * Kleopatra: Activating a profile no longer requires a restart
     of the affected components.

   * GpgOL: Improved error handling for encryption and decryption.

   * GpgOL: A possible crash when editing recipients has been fixed.
     (T3931)

   * GpgOL: The automatic recipient resolution has been improved.
     Among other things it now properly handles S/MIME as a fallback.
     (T3929)

   * GpgOL: The context menu of crypto mails now has the option to
     directly print the decrypted content. (T3762)

   * GnuPG: Update to version 2.2.7
     (See: https://lists.gnupg.org/pipermail/gnupg-announce/2018q2/000424.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.7
Kleopatra:      3.1.1
GPA:            0.9.10
GpgOL:          2.1.1
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.1.0 (2018-04-13)
------------------------------------------------

   * Kleopatra: Now offers a text editor for text based cryptography.
     (T3743)

   * Kleopatra: The extended certificate selection now offers import.
     (T3744)

   * Kleopatra: A crash when verifiying a detached signature has been fixed.
     (T3761)

   * Kleopatra: The advanced key generation now offers curve 25519. (T3826)

   * Kleopatra: Certificate details have been improved.

   * Kleopatra: Decrypting / verifiying multiple files at once has been fixed.
     (KDE-Bug: 391222)

   * Kleopatra: Serveral issues have been fixed, which occurred, if the
     Appdata directory was redirected to an UNC path. (T3818)

   * Kleopatra: Multiple minor improvements.
     (T3845 T3846 T3776 T3723 T3849 T3850 T3865 T3868)

   * GpgOL: Cryptographic functions are now called directly from GpgOL,
     without using Kleopatra. This fixes several problems caused by
     communication issues between Kleopatra and GpgOL. (T3509)

   * GpgOL: PGP/Inline (i.e. non-MIME) is now supported for sign and encrypt.
     This helps with compatibility problems like T3545.

   * GpgOL: Another issue was fixed, which could cause decrypted mails
     not to be displayed. (T3789)

   * GpgOL: Outlook should no longer loose focus after encrypting a mail.
     (T3732)

   * GpgOL: Basic support for Web Key publishing has been added. (T3785)

   * GpgOL: Additional mail types are now supported when reading.
     (T3802 T3882)

   * GpgOL: The handling of Exchange Mail addresses was improved. (T3082)

   * GpgOL: A problem that could cause mails to be stuck in the outbox has
     been fixed. (T3812)

   * GpgOL: Now trys harder to fixup broken PGP/Inline (no-MIME) Messages.
     (T3821)

   * GpgOL: Forwarding of encrypted / signed mails with attachments
     is now supported. (T3836)

   * GpgOL: S/MIME is supported again with the last version of Exchange
     2016. (T3853)

   * GpgOL: Re-sending crypto mails is now supported. (T3884)

   * GpgOL: An issue was resolved, which could lead to strange numbering
     of attachments. (T3886)

   * GnuPG: A rare problem that could lead to "General Error" messages
     after a fresh install of Gpg4win has been fixed. (T3839)

   * GnuPG: Updated to version 2.2.6.
     (See: https://lists.gnupg.org/pipermail/gnupg-announce/2018q2/000421.html )

~~~~~~~~~~~~~~~
GnuPG:          2.2.6
Kleopatra:      3.1.0
GPA:            0.9.10
GpgOL:          2.1.0
GpgEX:          1.0.6
Kompendium DE:  4.0.1
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.0.3 (2018-01-12)
------------------------------------------------

   * GnuPG: Updated to 2.2.4.

   * GpgOL: A bug that caused drafted mails not to encrypt the correct
     content has been fixed. (T3419)

   * GpgOL: A bug that caused encrypted mails not to be displayed has been
     fixed. (T3537)

   * GpgOL: A bug that caused sending unencrypted mails when Outlooks internal
     S/MIME code was activated has been fixed. (T3656)

   * GpgOL: PGP/Inline (no-mime) sending is now compatible with
     Microsoft Exchange Online. (T3662)

   * GpgOL: The recipient lookup for Exchange addresses has been
     improved.

   * GpgOL: Signatures of signed only mails with attachments have been
     fixed. (T3735)

   * GpgEX: An internal error when trying to verify a non-signature file
     has been fixed. (T3658)

   * Kleopatra: Sorting in Keylist has been fixed. (T3603)

   * Kleopatra: Certificate details for S/MIME certificates have been improved.
     (T3611, T3727, T3726)

   * Kleopatra: Certificates can now be exported as text from the certificate
     details. (T3605)

   * Kleopatra: The usage of the temp directory to buffer decrypted data is now
     configurable. (T3602)

   * Installer: The installer no longer reinstalls desktop shortcuts on
     upgrade. (T3729)

~~~~~~~~~~~~~~~
GnuPG:          2.2.4
Kleopatra:      3.0.2
GPA:            0.9.10
GpgOL:          2.0.6
GpgEX:          1.0.5
Kompendium DE:  4.0.0
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in Version 3.0.2 (2017-12-08)
------------------------------------------------

   * GnuPG: Two issues have been fixed that could block
     the GnuPG system. (T3378)

   * GpgOL: More possible "random" crashes caused by
     GpgOL have been fixed. (T3484)

   * GpgOL: Outlook is no longer blocked when selecting many mails.
     (T3433)

   * GpgOL: G Suite Sync plugin accounts are now detected. Only sending
     No-MIME PGP/Messages (without attachments) and unsigned
     messages are supported. Reading crypto mail is fully supported.
     (T3545)

   * GpgOL: The option to send "No-MIME" (inline) PGP encrypted,
     unsigned text messages without attachments works again. (T3514)

   * GpgOL: Improved error handling for signed, unencrypted mails.
     (T3538)

   * GpgOL: Several performance improvements.

   * GpgOL: Improved detection of large PGP/MIME messages and
     MS-TNEF crypto messages. (T3419 , T3542)

   * Kleopatra: Passphrase entry is no longer opened behind Kleopatra
     windows. (T3460)

   * Kleopatra: Decrypting archives across partitions has been fixed.
     (T3547)

   * Kleopatra: Fixed possible crash in GpgOL certificate selection.
     (T3544)

   * Kleopatra: Preselection of encrypt / sign file actions from GpgEX
     works again. (T3543)

   * Kleopatra: Added Web Key Directory lookup support in file
     encryption dialog. (T3548)

   * Kleopatra: Fixed crash when searching in LDAP. (T3550)

   * Kleopatra: Fixed crash when aborting key generation. (T3577)

   * Kleopatra: Certifications are accessible again from the certificate
     details view. (T3579)

   * Kleopatra: It is now possible to publicly certify an already locally
     signed certificate. (T1649)

~~~~~~~~~~~~~~~
GnuPG:          2.2.3
Kleopatra:      3.0.1
GPA:            0.9.9
GpgOL:          2.0.5
GpgEX:          1.0.5
Kompendium DE:  4.0.0
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in Version 3.0.1 (2017-11-21)
------------------------------------------------

   * GpgOL: A cause for seemingly random crashes in Outlook has been
     fixed.

   * GpgOL: A crash when pasting recipients has been fixed.

   * GpgOL: Various problems regarding S/MIME mails have been fixed.

   * GpgOL: A user interface error for Outlook 2010 has been fixed.

   * GpgOL: Kleopatra is again started in the background to speed
     up crypto operations.

   * Kleopatra: Various problems regarding S/MIME file operations
     have been fixed.

   * Kleopatra: Various problems regarding folder operations and
     archives have been fixed.

   * GnuPG: Has been updated to version 2.2.3.

   * Some small bugfixes and improvements.

   * The mkportable process can be used again to create a portable
     Gpg4win variant.

~~~~~~~~~~~~~~~
GnuPG:          2.2.3
Kleopatra:      3.0.1
GPA:            0.9.9
GpgOL:          2.0.3
GpgEX:          1.0.5
Kompendium DE:  4.0.0
Compendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 3.0.0 (2017-09-19)
------------------------------------------------
   * German compendium is now updated to Version 4.0. It is
     adjusted to the changes made in Gpg4win 3.0.

   * GnuPG is now of the modern 2.2 variant. See:
     https://lists.gnupg.org/pipermail/gnupg-announce/2017q3/000413.html
     for more information about this.

   * GpgOL is now also supported for Outlook 64 bit.

   * GpgOL for Outlook 2010 and later, now uses toggle buttons
     to let you select Encrypt and Sign. The operations are done
     when the mail is sent, including all attachments,
     using a standard format (MIME).

   * GpgOL for Outlook 2010 and later, now automatically decrypts emails
     again.

   * All 68 KDE translations for Kleopatra are now included in Gpg4win.

   * Kleopatra uses an updated icon theme.

   * Kleopatra now shows the used curve for ECC keys under `technical
     details`.

   * Kleopatra has been updated to a new set of base libraries.

   * Binaries are now all installed in a `bin` sub-directory. DBus
     and kbuildsycoa are no longer required. This fixes the startup issues
     of Kleopatra some users were facing.

   * After importing a secret key in Kleopatra you will be asked to directly
     mark it as your own key (ownertrust).

   * Kleopatra now allows you to create ECC keys in the `advanced settings`
     during key generation.

   * Kleopatras file menu now also offers to encrypt folders.

   * Kleopatra has a new option to print a secret key using the tool `paperkey`.

   * GPA and Kleopatra are now registered with Windows for OpenPGP and S/MIME
     related file extensions.

   * The file encryption dialog in Kleopatra has been redesigned
     to reduce steps and improve user experience.

   * Kleopatra automatically detects the type of an input file
     and automatically starts the corresponding action (e.g. decrypt).

   * Symmetric (password only) encryption is now accessible through
     Kleopatra and can be combined with public-key encryption.

   * Pinentry now enables you to inspect the typed passphrase.

   * Kleopatra now supports OpenPGP smartcard management.

   * GpgOL for Outlook 2010 and later, has a new interface to show
     the signature / encryption state inside of Outlook.

   * GnuPG now supports https and uses the https sks-keyserver pool
     by default.

   * GpgOL now supports sending and receiving HTML Mails

   * Kleopatra has improved file verification messages.

   * Kleopatra now supports to directly import missing certificates
     when verifying a file.

   * Many bugfixes and minor improvements.

~~~~~~~~~~~~~~~
GnuPG:          2.2.1
Kleopatra:      3.0.0
GPA:            0.9.9
GpgOL:          2.0.1
GpgEX:          1.0.5
Kompendium DE:  4.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.3.1 (2016-04-05)
------------------------------------------------

   * GpgOL now has an option dialog where S/MIME can be disabled.

   * GpgOL now supports the 64 Bit version of Microsoft Outlook.

   * GpgOL can be switched to the new, experimental, MIME aware behavior in
     the Options Dialog.

   * GpgOL now reverts temporary changes made to MIME mails. So that they
     can be opened with other clients again.

   * GpgEX no longer blocks the Windows Explorer while it starts GPA or
     Kleopatra.

~~~~~~~~~~~~~~~
GnuPG:          2.0.30
Kleopatra:      2.2.0-gitfb4ae3d
GPA:            0.9.9
GpgOL:          1.4.0
GpgEX:          1.0.4
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.3.0 (2015-11-25)
------------------------------------------------

   * GpgOL now supports reading PGP/MIME and S/MIME mails, the standard
     format for Crypto Mails as sent by Thunderbird/Enigmail, GPGMail
     or KMail. For details see: https://wiki.gnupg.org/GpgOL/MIMESupport

   * GpgOL now supports Outlook 2016.

   * AES-NI Instructions for faster encryption and decryption with AES
     are now supported. (GnuPG Bug #1919)

   * The decrypt/verify window of GpgOL no longer moves and resizes
     erratically. (KDE Bug #355140)

   * Bulk import of more then a hundred keys no longer fails when Kleopatra
     is running. (GnuPG Bug #2135)

   * French and Chinese localisation has been added to the installer,
     GpgEX and GpgOL. Thanks to Oliver Serve and Mingye Wang.

   * Several apparently random crashes in GpgOL have been fixed
     (GnuPG Bug #1837)

   * GpgOL now handles attachments in  PGP/MIME and S/MIME mails with non ASCII
     characters in the filename correctly.

   * A vulnerability in the Gpg4win-installer has been fixed. See:
     [security advisory 2015-11-25] for details.

~~~~~~~~~~~~~~~
GnuPG:          2.0.29
Kleopatra:      2.2.0-gitfb4ae3d
GPA:            0.9.9
GpgOL:          1.3.0
GpgEX:          1.0.3
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in version 2.2.6 (2015-09-09)
------------------------------------------------

   * Claws Mail has been removed from the package. Users of
     Claws Mail should switch to the version maintained by
     the Claws Mail initiative available on:
         http://www.claws-mail.org/win32/

   * GnuPG has been updated to Version 2.0.29.

   * X509 Certificate requests can now again generated with
     default options.

   * GPA has been updated to Version 0.9.9.

~~~~~~~~~~~~~~~
GnuPG:          2.0.29
Kleopatra:      2.2.0-gitcf609810
GPA:            0.9.9
GpgOL:          1.2.1
GpgEX:          1.0.2
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in version 2.2.5 (2015-07-10)
------------------------------------------------

   * GnuPG has been updated to version 2.0.28. See release notes on
     www.gnupg.org for details.

   * A potential crash during certificate search has been fixed.

   * Kleopatra no longer queries revocation information for X509
     certificates during startup. This will drastically improve
     the startup time for some users.
     Revocation information is still checked once a certificate is used.

   * Kleopatra now uses the same defaults as GnuPG for new OpenPGP
     certificates.

   * Third party libraries included in Gpg4win have been updated.

~~~~~~~~~~~~~~~
GnuPG:          2.0.28
Kleopatra:      2.2.0-gita3c9200
GPA:            0.9.7
GpgOL:          1.2.1
GpgEX:          1.0.2
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in version 2.2.4 (2015-03-17)
------------------------------------------------
   * GnuPG has been updated to version 2.0.27. See release notes on
     www.gnupg.org for details.

   * Libgcrypt has been updated to version 1.6.3 (includes fix for
     CVE-2014-3591)

   * An issue has been fixed which could cause extracted files from
     TAR Archives to be truncated.

~~~~~~~~~~~~~~~
GnuPG:          2.0.27
Kleopatra:      2.2.0-git945878c
GPA:            0.9.7
GpgOL:          1.2.1
GpgEX:          1.0.1
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in version 2.2.3 (2014-11-25)
------------------------------------------------
   * The vanilla installer has been fixed by including GnuTLS.

   * Creation of portable versions with mkportable has been fixed.

   * GPA now works again under Windows XP.

   * Verification of a detached signature without specifying what
     should be verified may now show a warning and has been disabled
     in batch mode.

   * Tar archives can now include files and folders that use
     special characters (e.g. umlauts) which can be encoded
     in the native Windows 8-Bit codepage.

   * Kleopatra now handles preprocessing (e.g. archiving) errors
     and safely aborts the operation.

   * GPA has been updated to version 0.9.6.

   * A security problem in the libksba library has been fixed.

~~~~~~~~~~~~~~~
GnuPG:          2.0.26
Kleopatra:      2.2.0-git945878c
GPA:            0.9.6
GpgOL:          1.2.1
GpgEX:          1.0.1
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~

Noteworthy changes in version 2.2.2 (2014-09-03)
------------------------------------------------

   * GnuPG has been updated to version 2.0.26. See release notes on
     www.gnupg.org for details.

   * Sreen reader support and accessibility of Kleopatra was improved.

   * A library load problem has been fixed that could keep Kleopatra
     from starting on some systems.

   * Kleopatra has been updated to KDE Sofware Collection 4.14.

   * Used libraries have been updated to their latest stable relase.

   * GpgEX no longer crashes if the environment variable GNUPGHOME is set.

   * Pinentry-qt warning and confirmation dialogs should now open always in
     foreground.

   * Problems with Outlook sender and recipient address lookup have been
     fixed in GpgOL. Especially for Microsoft Exchange addresses.

   * Command line output is encoded to the Windows console encoding.

   * The pinentry dialog is now translated correctly in the French locale.

   * Command line wildcards (like *.txt) work again.

~~~~~~~~~~~~~~~
GnuPG:          2.0.26
Kleopatra:      2.2.0-gitac229d2
GPA:            0.9.4
GpgOL:          1.2.1
GpgEX:          1.0.1
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.2.1 (2013-10-08)
------------------------------------------------

   * Fixed possible infinite recursion in the compressed packet
   parser. [CVE-2013-4402]

   * Kleopatra no longer crashes when using Microsoft Office IME.

   * Support for SPR332 and 532 pinpads.

~~~~~~~~~~~~~~~
GnuPG:          2.0.22
Kleopatra:      2.2.0
GPA:            0.9.4
GpgOL:          1.2.0
GpgEX:          1.0.0
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.2.0 (2013-08-20)
------------------------------------------------

   * GpgEx now works on Windows 64 bit.

   * Gpg-agent may now be used as Pageant (PuTTY authentication agent)
     replacement with additional smartcard support.

   * Pinentry now allows to paste in the passphrase.

   * Kleopatra no longer crashes when started by a regular user on
     terminal servers (Windows Server).

   * GpgOL provides rudimentary support for Outlook 2010 and 2013.
     The following crypto functions are already available via the new
     GpgOL ribbon rsp. Outlook's context menu (no MIME parsing, yet):
     - Encrypting/decrypting mail bodys
     - Saving and decrypting attachments
     - Attaching and encrypting files
     - Signing and signature verification (of opaque signatures)

   * Extracting a tarball through the Kleopatra GUI now works reliable

   * Added mkportable.exe as a tool to create a portable installation.

   * Kleopatra now allows it to generate keys with a size up to 4096 bit.

~~~~~~~~~~~~~~~
GnuPG:          2.0.21
Kleopatra:      2.2.0
GPA:            0.9.4
GpgOL:          1.2.0
GpgEX:          1.0.0
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.1.1 (2013-05-28)
------------------------------------------------

   * New versions of GnuPG, GpgOL, GPA, Kleopatra, and Claws-Mail.

   * Development files for the crypto libraries will now be installed.

~~~~~~~~~~~~~~~
GnuPG:          2.0.20
Kleopatra:      2.1.1
GPA:            0.9.4
GpgOL:          1.1.3
GpgEX:          0.9.7
Claws-Mail:     3.9.1
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0-beta1
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.1.0 (2011-03-15)
------------------------------------------------

   * New versions of GnuPG, Kleopatra, GpgEX, GpgOL, Claws.

~~~~~~~~~~~~~~~
GnuPG:          2.0.17
Kleopatra:      2.1.0 (2011-02-04)
GPA:            0.9.1-svn1024
GpgOL:          1.1.2
GpgEX:          0.9.7
Claws-Mail:     3.7.8cvs47
Kompendium DE:  3.0.0
Kompendium EN:  3.0.0-beta1
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.0.4 (2010-07-28)
------------------------------------------------

   * GpgSM bug fix.

~~~~~~~~~~~~~~~
GnuPG:        2.0.14 + 02-gpgsm-realloc-bug.patch
Kleopatra:    2.0.14-svn1098530 (20100303)
GPA:          0.9.0
GpgOL:        1.1.1
GpgEX:        0.9.5
Claws-Mail:   3.7.4cvs1
Kompendium:   3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.0.3 (2010-05-29)
------------------------------------------------

   * Bug fixes.

~~~~~~~~~~~~~~~
GnuPG:        2.0.14
Kleopatra:    2.0.14-svn1098530 (20100303)
GPA:          0.9.0
GpgOL:        1.1.1
GpgEX:        0.9.5
Claws-Mail:   3.7.4cvs1
Kompendium:   3.0.0
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.0.2 (2010-04-12)
------------------------------------------------

   * Bug fixes and UI improvements.

~~~~~~~~~~~~~~~
GnuPG:        2.0.14
Kleopatra:    2.0.14-svn1098530 (20100303)
GPA:          0.9.0
GpgOL:        1.1.1
GpgEX:        0.9.5
Claws-Mail:   3.7.4cvs1
Kompendium:   3.0.0-rc1
~~~~~~~~~~~~~~~


Noteworthy changes in version 2.0.1 (2009-09-28)
------------------------------------------------

   * Fixed a problem opening Office documents and URLs with a running
     GpgOL.

~~~~~~~~~~~~~~~
GnuPG:        2.0.12
Kleopatra:    2.0.11-svn1008232 (2009-09-25)
GPA:          0.9.0
GpgOL:        1.0.1
GpgEX:        0.9.3
Claws-Mail:   3.7.2cvs27
Kompendium:   3.0.0-beta4
~~~~~~~~~~~~~~~



Noteworthy changes in version 2.0.0 (2009-08-07)
------------------------------------------------

   * First production release of this major redesign.  Over the last
     15 months we did 15 beta releases and hopefully squashed most of
     the serious bugs.

~~~~~~~~~~~~~~~
GnuPG:        2.0.12
Kleopatra:    20090807
GPA:          0.9.0
GpgOL:        1.0.0
GpgEX:        0.9.3
Claws-Mail:   3.7.2
Kompendium:   3.0.0-beta3
~~~~~~~~~~~~~~~


For older news see the file ONEWS in the source distribution.



5. Versionsnummern der einzelnen Programmteile
==============================================

Zur ?bersicht sind hier die Pr?fsummen, sowie die Namen der einzelnen
Bestandteile, aufgelistet.

=========== SHA-1 checksum ============= == package ==
3c31c9d6b19af840e2bd8ccbfef4072a6548dc4e atk-1.32.0.zip
d0b8c53e01e4541d3d3befc82e41fb5b84949030 atk-dev-1.32.0.zip
7f56ab507d3258610391b47fef6b11635861175a boost-1.60.0.tar.bz2
9328201be1c0de6305638779f6ff9802ce033d42 breeze-icons-5.77.0.tar.xz
6e38be3377340a21a1f13ff84b5e6adce97cd1d4 bzip2-1.0.6-g10.tar.gz
d44cd66a9f4d7d29a8f2c28d1c1c5f9b0525ba44 cairo-1.10.2.zip
45cae1fac45a6c6f33498c37c0cdc47722614d92 cairo-dev-1.10.2.zip
f47790b9e324cd8613acc9a17fd56bf2c14745fc expat-2.0.1.zip
2e9189c6c6d1dac847a47c537c7a5e9dffd91992 expat-dev-2.0.1.zip
f8bfb9d8782c8e6c11260d4e0a378a04257b0ec6 extra-cmake-modules-5.77.0.tar.xz
37a3117ea6cc50c8a88fba9b6018f35a04fa71ce fontconfig-2.8.0.zip
0b772aaeb0a7a0d5de21afd901d6cf00753efa51 fontconfig-dev-2.8.0.zip
c20ab9ff053fe59f73612fd392f6e6dc01af614a freetype-2.4.2.zip
00e877d7ec7c416e2b48a392324a5502019a20bf freetype-dev-2.4.2.zip
6277b4e5b5e334b3669f15ae0376e184be9e8cd8 gdk-pixbuf-2.30.8.tar.xz
dc551d4783edf691c1f0095ca927d3128b5093e8 gettext-0.19.8.tar.xz
31de819181dd8abc25d89484ff6a4e60f032e8fc glib-2.41.5.tar.xz
9f2ff2ce36b6537f895ab3306527f105ff95df8d gnupg-w32-2.2.27-20210111-bin.exe
61475989acd12de8b7daacd906200e8b4f519c5a gpa-0.10.0.tar.bz2
2658f0c52f749576a5753c8a0572a45d2051da9b gpg4win-tools-202101081127.tar.gz
443270219d542f97b6f124d2101ae8d803c6dbe2 gpgex-1.0.6.tar.bz2
5ae07a303fcf9cec490dabdfbc6e0f3b8f6dd5a0 gpgme-1.15.1.tar.bz2
bde79b7f83c2c885fa5e9d4cf0abf5a7038d3799 gpgol-2.4.10.tar.bz2
f3c2f1a3728ed51d08054f6b4c7384fbf99477c0 gtk+-2.24.28.tar.xz
183f409aa46e8780b8475437cc39f20dc6c6fe77 karchive-5.77.0.tar.xz
ab652ef270112d24b0a6a0507b1872898354b7ea kcodecs-5.77.0.tar.xz
c06417e994b6c250f9e54048fe8f36626bbbf101 kcompletion-5.77.0.tar.xz
2ec2410ed5eebc942b858695e662e538a0a163d5 kconfig-5.77.0.tar.xz
ffcfbd96b5fc0bbb2fa2409bbd1ab10314dc2383 kconfigwidgets-5.77.0.tar.xz
30e2f3767262b69e4050f7ad697ba6dc602f5946 kcoreaddons-5.77.0.tar.xz
3e57376285cec75aa2a3a5b5672cfdb0c50da603 kcrash-5.77.0.tar.xz
3db28cce783aeb5f5d2b99ae1e288c3ec789b168 kde-l10n-202101071558-bin.tar.xz
d8348fcf389276105a7038762c06ca462b136a0b kguiaddons-5.77.0.tar.xz
849bd0716ebd704581428b9f499e6e3502352cb5 ki18n-5.77.0.tar.xz
d838f37460161c11f1813dd526bb3b8ea398b034 kiconthemes-5.77.0.tar.xz
b5056c9427d5b07d069d06253f103a13b04a3e49 kitemmodels-5.77.0.tar.xz
e97fae2b755b8c8c2aa1723aa5aeb18d28c8d6bb kitemviews-5.77.0.tar.xz
f338959db62c313eda26d72f3d84e4a6fc6a87d4 kleopatra-202101120902.tar.gz
78c4227ada3b24f968588dec64589ff277507577 kmime-19.08.3.tar.xz
00c6aab10f7d85af6fab26b6249c8ac43d234ea5 kwidgetsaddons-5.77.0.tar.xz
8ed1caaa238ee8b16d383c95e842d94e444c46bc kwindowsystem-5.77.0.tar.xz
b60c8d2035ec196368d53f00e2ad3c393ffdddb3 kxmlgui-5.77.0.tar.xz
55a35918e95566ef94e8843879a7dd3f87de3781 libassuan-2.5.4.tar.bz2
f5230890dc0be42fb5c58fbf793da253155de106 libffi-3.0.13.tar.gz
66d6270511a48bac0bf347330e7a12c62f3a1ab4 libgpg-error-1.41.tar.bz2
7af3149fa7c4bd1d3a36a30f02e95a0ebfd6b18f libiconv-1.15.tar.gz
ffb031256f0136579abdbbc01c566283f01decd5 libkleo-202101120903.tar.gz
382f820db7adac5e31605c5fa93ba98ff0e94049 libpng-1.4.22.tar.xz
3959319bd04fbce513458857f334ada279b8cdd4 pango-1.29.4.zip
49ae12458f2e29c27ed9d1390d95db18fd4a49ac pango-dev-1.29.4.zip
2d11d78f1c483bc07479a131bc2b04bac3c87282 paperkey-1.5.tar.gz
b21029060cae67c294da2109e2b0434c0f727234 pinentry-1.1.1-beta44.tar.bz2
d063e705812e1ee7feb8f35d51b3cad04ca13b0d pkgconfig-0.23.zip
f5191757d1125aa7750a3f5d39321490477cfb65 qtbase-5.15.0.tar.xz
6da4345fcb676f8483c282dee1366db31370775b qtsvg-5.15.0.tar.xz
9b5ea97ebe7e3e3be118060b42293c4237a465de qttools-5.15.0.tar.xz
fb7b76c23df5ececfbce35a8f5ffba987807194a qttranslations-5.15.0.tar.xz
f4aa75fbd73c18861abf485697d223cc7482f6e4 qtwinextras-5.15.0.tar.xz
3f8a0ba9c7821049d51b982141a2330a246beb55 scute-1.7.0.tar.bz2
d648b98ce215f81e901f3f982470d37c704433a6 w32pth-2.0.5.tar.bz2
e6d119755acdf9104d7ba236b1242696940ed6dd zlib-1.2.11.tar.gz


6. Rechtliche Hinweise zu den einzelnen Bestandteilen der Software
==================================================================

Gpg4win besteht aus einer ganzen Reihe von unabh?ngig entwickelten
Paketen, die teilweise unterschiedliche Lizenzen haben. Der Gro?teil
dieser Software ist, wie Gpg4win selbst, kompatibel mit der GNU General
Public License (GNU GPL). Allen gemeinsam ist, dass es Freie Software ist,
welche ohne Restriktionen benutzt werden kann, studiert und ver?ndert werden
darf, sowie, dass ?nderungen weitergeben d?rfen. Wenn die Quelltexte (also
gpg4win-x.y.z.tar.bz2) mit weitergegeben werden und auf die die GNU
GPL hingewiesen wird, ist die Weitergabe fast immer m?glich.

Zur ?bersicht folgt eine Liste der Copyright Erkl?rungen.


Here is a list with collected copyright notices.  For details see the
description of each individual package.  This is not meant as an
exhaustive list of copyright notices.  Notices from several packages
are even not listed.  The license with the highest freedom protection is
the GNU General Public License version 3 (GPLv3+); thus complying to
those terms and conditions should be sufficient.  If in doubt check
the individual packages.


Gpg4win (the installer) is

  Copyright (C) 2005-2013 g10 Code GmbH
                2013-2018 Intevation GmbH
                2019      g10 Code GmbH
                2015-2018 Bundesamt für Sicherheit in der Informationstechnik
                          Software Engineering by Intevation GmbH

  Gpg4win is free software; you can redistribute it and/or modify it
  under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 2 of the License, or
  (at your option) any later version.

  Gpg4win is distributed in the hope that it will be useful, but
  WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with this program; if not, write to the Free Software
  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA
  02110-1301, USA


GnuPG is

  Copyright 1998-2019 Free Software Foundation, Inc.

  GnuPG is free software; you can redistribute it and/or modify it
  under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 3 of the License, or
  (at your option) any later version.

  GnuPG is distributed in the hope that it will be useful, but WITHOUT
  ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
  or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public
  License for more details.

  You should have received a copy of the GNU General Public License
  along with this program; if not, see <http://www.gnu.org/licenses/>.

  See the files AUTHORS and THANKS for credits, further legal
  information and bug reporting addresses pertaining to GnuPG.


NSIS is

  Copyright 1999-2009 Nullsoft, Jeff Doozan and Contributors
  Copyright 2002-2008 Amir Szekely
  Copyright 2003 Ramon
  Copyright 1995-1998 Jean-loup Gailly and Mark Adler
  Copyright 1999-2006 Igor Pavlov
  Copyright 1996-2000 Julian R Seward

  This license applies to everything in the NSIS package, except where
  otherwise noted.

  This software is provided 'as-is', without any express or implied
  warranty. In no event will the authors be held liable for any
  damages arising from the use of this software.

  Permission is granted to anyone to use this software for any
  purpose, including commercial applications, and to alter it and
  redistribute it freely, subject to the following restrictions:

  1. The origin of this software must not be misrepresented; you must
     not claim that you wrote the original software. If you use this
     software in a product, an acknowledgment in the product
     documentation would be appreciated but is not required.

  2. Altered source versions must be plainly marked as such, and must
     not be misrepresented as being the original software.

  3. This notice may not be removed or altered from any source
     distribution.

  The user interface used with the installer is

  Copyright (C) 2002-2005 Joost Verburg

  [It is distributed along with NSIS and the same conditions as stated
   above apply]


GLIB is

  Copyright (C) 1995-1997 Peter Mattis, Spencer Kimball and Josh MacDonald
  Copyright (C) 1995-2011 Red Hat, Inc.
  Copyright (C) 2008-2010 Novell, Inc.
  Copyright (C) 2008-2010 Codethink Limited.
  Copyright (C) 2008-2010 Collabora, Ltd.

  This library is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2 of the License, or (at your option) any later version.

  This library is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.	 See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this library; if not, write to the
  Free Software Foundation, Inc., 59 Temple Place - Suite 330,
  Boston, MA 02111-1307, USA.

  See the AUTHORS file for a list of people on the GLib Team.  See the
  ChangeLog files for a list of changes.  These files are distributed
  with GLib at ftp://ftp.gtk.org/pub/gtk/.


GPA is

  Copyright (C) 2000-2002 G-N-U GmbH (http://www.g-n-u.de)
  Copyright (C) 2002-2003 Miguel Coca.
  Copyright (C) 2005-2019 g10 Code GmbH

  GPA uses fragments from the following programs and libraries:
  JNLIB, Copyright (C) 1998-2000 Free Software Foundation, Inc.
  GPGME, Copyright (C) 2000-2001 Werner Koch
  WinPT, Copyright (C) 2000-2002 Timo Schulz
  (For details, see the file `AUTHORS'.)

  GPA is free software; you can redistribute it and/or modify it
  under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 3 of the License, or
  (at your option) any later version.

  GPA is distributed in the hope that it will be useful, but
  WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
  GNU General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with this program; if not, see <http://www.gnu.org/licenses/>.


GPGEX is

  Copyright (C) 2007-2019 g10 Code GmbH

  GpgEX is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2 of the License, or (at your option) any later version.

  GpgEX is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
  GNU Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this program; if not, write to the Free Software
  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA
  02110-1301, USA.


GPGME is

  Copyright (C) 2000 Werner Koch
  Copyright (C) 2001-2019 g10 Code GmbH
                2015-2019 Bundesamt für Sicherheit in der Informationstechnik
                          Software Engineering by Intevation GmbH

  GPGME is free software; you can redistribute it and/or modify it
  under the terms of the GNU Lesser General Public License as
  published by the Free Software Foundation; either version 2.1 of
  the License, or (at your option) any later version.

  GPGME is distributed in the hope that it will be useful, but
  WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this program; if not, see <http://www.gnu.org/licenses/>.

  See the files AUTHORS and THANKS for credits, further legal
  information and bug reporting addresses pertaining to GPGME.


GpgOL is

  Copyright (C) 2004-2011 g10 Code GmbH
                2015-2018 Bundesamt für Sicherheit in der Informationstechnik
                          Software Engineering by Intevation GmbH
                2013-2018 Intevation GmbH
                     2019 g10 Code GmbH

  GpgOL is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2 of the License, or (at your option) any later version.

  GpgOL is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
  GNU Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this program; if not, see <http://www.gnu.org/licenses/>.

  See the files AUTHORS and THANKS for credits, further legal
  information and bug reporting addresses pertaining to GpgOL.


GTK+ is

  Copyright (C) 1995-1997 Peter Mattis, Spencer Kimball and Josh MacDonald

  This library is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2 of the License, or (at your option) any later version.

  This library is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this library; if not, write to the
  Free Software Foundation, Inc., 59 Temple Place - Suite 330,
  Boston, MA 02111-1307, USA.

  Modified by the GTK+ Team and others 1997-2000.  See the AUTHORS
  file for a list of people on the GTK+ Team.  See the ChangeLog
  files for a list of changes.  These files are distributed with
  GTK+ at ftp://ftp.gtk.org/pub/gtk/.


LIBGCRYPT is

  Copyright (C) 1989,1991-2016· Free Software Foundation, Inc.
                1994 X Consortium
                1996 L. Peter Deutsch
                1997 Werner Koch
                1998 The Internet Society
                1996-1999 Peter Gutmann, Paul Kendall, and Chris Wedgwood
                1996-2006 Peter Gutmann, Matt Thomlinson and Blake Coverett
                2003 Nikos Mavroyanopoulos
                2006-2007 NTT (Nippon Telegraph and Telephone Corporation)
                2012-2019 g10 Code GmbH
                2012 Simon Josefsson, Niels Möller
                2012 Intel Corporation
                2013 Christian Grothoff
                2013-2019 Jussi Kivilinna
                2013-2014 Dmitry Eremin-Solenikov
                2014 Stephan Mueller

  Libgcrypt is free software; you can redistribute it and/or modify
  it under the terms of the GNU Lesser general Public License as
  published by the Free Software Foundation; either version 2.1 of
  the License, or (at your option) any later version.

  Libgcrypt is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
  GNU Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this program; if not, see <http://www.gnu.org/licenses/>.


LIBGPG-ERROR is

  Copyright (C) 2001-2004, 2010, 2012-2019, g10 Code GmbH

  libgpg-error is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public License
  as published by the Free Software Foundation; either version 2.1 of
  the License, or (at your option) any later version.

  libgpg-error is distributed in the hope that it will be useful, but
  WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this program; if not, see <http://www.gnu.org/licenses/>.


Pthreads-win32 is

  Copyright(C) 1998 John E. Bossom
  Copyright(C) 1999,2005 Pthreads-win32 contributors

  Most of this is work available under the GNU Lesser General Public
  License as published by the Free Software Foundation version 2.1 of
  the License.  The detailed terms are given in the file COPYING in
  the source distribution; that very file may not be modified and thus
  it is not possible to include it here.


BZIP2 is

  This program, "bzip2", the associated library "libbzip2", and all
  documentation, are copyright (C) 1996-2006 Julian R Seward.  All
  rights reserved.

  Redistribution and use in source and binary forms, with or without
  modification, are permitted provided that the following conditions
  are met:

  1. Redistributions of source code must retain the above copyright
     notice, this list of conditions and the following disclaimer.

  2. The origin of this software must not be misrepresented; you must
     not claim that you wrote the original software.  If you use this
     software in a product, an acknowledgment in the product
     documentation would be appreciated but is not required.

  3. Altered source versions must be plainly marked as such, and must
     not be misrepresented as being the original software.

  4. The name of the author may not be used to endorse or promote
     products derived from this software without specific prior written
     permission.

  THIS SOFTWARE IS PROVIDED BY THE AUTHOR ``AS IS'' AND ANY EXPRESS
  OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
  WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
  ARE DISCLAIMED.  IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY
  DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
  DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE
  GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
  INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING
  NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
  SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

  Julian Seward, Cambridge, UK.
  jseward@bzip.org
  bzip2/libbzip2 version 1.0.4 of 20 December 2006


ADNS

  adns is Copyright 2008 g10 Code GmbH, Copyright 1997-2000,2003,2006
  Ian Jackson, Copyright 1999-2000,2003,2006 Tony Finch, and Copyright
  (C) 1991 Massachusetts Institute of Technology.

  adns is free software; you can redistribute it and/or modify it
  under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 2 of the License, or
  (at your option) any later version.

  This program and documentation is distributed in the hope that it will
  be useful, but without any warranty; without even the implied warranty
  of merchantability or fitness for a particular purpose. See the
  GNU General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with adns, or one should be available above; if not, write to
  the Free Software Foundation, 59 Temple Place - Suite 330, Boston,
  MA 02111-1307, USA, or email adns-maint@chiark.greenend.org.uk.


Paperkey

  Copyright (C) 2007, 2008, 2009 David Shaw <dshaw@jabberwocky.com>

  This program is free software; you can redistribute it and/or modify
  it under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 2 of the License, or
  (at your option) any later version.

  This program is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
  GNU General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with this program; if not, write to the Free Software
  Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston,
  MA 02110-1301, USA.

  The included man page is

  Copyright (C) 2007 Peter Palfrader <peter@palfrader.org>

  Examples have been taken from David Shaw's README. The license is
  the same as for Paperkey.


Scute

  Copyright 2006, 2008 g10 Code GmbH

  Scute is licensed under the GNU General Pubic License, either
  version 2, or (at your option) any later version with this special
  exception:

  In addition, as a special exception, g10 Code GmbH gives permission
  to link this library: with the Mozilla Foundation's code for
  Mozilla (or with modified versions of it that use the same license
  as the "Mozilla" code), and distribute the linked executables.  You
  must obey the GNU General Public License in all respects for all of
  the code used other than "Mozilla".  If you modify the software, you
  may extend this exception to your version of the software, but you
  are not obligated to do so.  If you do not wish to do so, delete this
  exception statement from your version and from all source files.


KDE-Frameworks

  This library is free software; you can redistribute it and/or
  modify it under the terms of the GNU Lesser General Public
  License as published by the Free Software Foundation; either
  version 2.1 of the License, or (at your option) version 3, or any
  later version accepted by the membership of KDE e.V. (or its
  successor approved by the membership of KDE e.V.), which shall
  act as a proxy defined in Section 6 of version 3 of the license.

  This library is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  Lesser General Public License for more details.

  You should have received a copy of the GNU Lesser General Public
  License along with this library.  If not, see <http://www.gnu.org/licenses/>.

Kleopatra

  Copyright (C):
           2002-2003, Marc Mutz <mutz@kde.org>
           2008, Nokia Corporation and/or its subsidiary(-ies)
           2001-2010, Klarälvdalens Datakonsult AB
           2015-2018, Intevation GmbH
           2015-2018, Bundesamt für Sicherheit in der Informationstechnik
                      Software Engineering by Intevation GmbH
                2019, g10 Code GmbH

  Kleopatra is free software; you can redistribute it and/or modify
  it under the terms of the GNU General Public License as published by
  the Free Software Foundation; either version 2 of the License, or
  (at your option) any later version.

  Kleopatra is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
  General Public License for more details.

[Compiled by wk 2006-02-15, last updated 2019-04-02]


*** Ende der Datei ***
