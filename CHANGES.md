# Revision history for Perl extension Win32::EventLog

## 0.079 [2026-05-05]

- fix skipped record in SEQUENTIAL ReadEventLog (RT#61484) by Olivier Mengué.
  OFFSET is ignored in SEQUENTIAL read, matching the underlying Win32 API;
  previously a '0' value bypassed the cache and gave unpredictable results
- refactor ReadEventLog SEEK mode to use cached entries instead of
  re-reading on every call by Olivier Mengué
- add test for RT#61484 by Olivier Mengué (now also listed in MANIFEST so
  it ships in the CPAN tarball)

## 0.078 [never released]

- tagged on the repo but never reached CPAN: the release workflow's
  manifest_check rejected the tarball because t/RT61484.t was not listed
  in MANIFEST. Superseded by 0.079 with the same code changes plus the
  MANIFEST fix.
- fix POD typos by David Steinbrunner (@dsteinbrunner) [#2](https://github.com/perl-libwin32/win32-eventlog/pull/2)
- add GitHub repository URL to META.yml by David Steinbrunner (@dsteinbrunner) [#1](https://github.com/perl-libwin32/win32-eventlog/pull/1)
- fix required perl version 5.6 -> 5.006 by David Steinbrunner (@dsteinbrunner) [#3](https://github.com/perl-libwin32/win32-eventlog/pull/3)
- add INSTALL file with build hints by Alexandr Ciornii
- move repository to perl-libwin32 organization [#4](https://github.com/perl-libwin32/win32-eventlog/pull/4)
- add LICENSE and README.md [#5](https://github.com/perl-libwin32/win32-eventlog/pull/5)
- drop redundant "from Perl" from abstract
- normalize line endings to LF

## 0.076 [2008-07-02]

- Make sure the regression tests are properly skipped on Win95

## 0.075 [2008-04-15] by Jan Dubois

- version 0.075 for separate upload to CPAN
- simplified Makefile.PL
- added META.yml
- added ppport.h
- fixes for Win64 support

## 0.074 [unreleased]

- EventLog can sometimes fail to retrieve messages (fix suggested
  by Patrice M. I. Parmentier in
  http://rt.perl.org/rt2/Ticket/Display.html?id=17457)

## 0.073 [2002-05-17] by Brett Williams

- fix for incorrect number of parameters passed from method
  Win32::EventLog::Report to method Win32::EventLog::WriteEventLog
- fix for method Win32::EventLog::WriteEventLog ignoring 'reserved'
  parameter

## 0.072 [2001-08-14] by Jan Dubois

- GetEventLogText fixes:
- EventMessageFile can actually be a *list* of files
- provide additional bogus inserts to cope with broken
  message files / eventlog entries

## 0.071 [2000-08-25] by Jan Dubois

- remove limit of 16 fields for GetEventLogText
- fix endless loop problem in GetEventLogText

## 0.07 [2000-05-22]

- support for passing Unicode strings to underlying calls (thanks
  to Jan Dubois)
- various other cleanups for the code and the documentation
  (Jan Dubois)

## 0.062 [2000-05-22]

- fix for memory leak in EventLog due to lack of DESTROY()
  (suggested by Jan Dubois)
- Report() method uses 'Source' and 'Computer' fields in passed
  hashref if they exist, and uses the same fields from the EventLog
  object if they don't.  NOTE: THIS IS A POTENTIAL COMPATIBILITY
  ISSUE.

## 0.06 [1999-02-02]

- new method overloaded to support backup eventlogs
- GetEventLogText now processes embedded %%xxx strings.
- Automatic call to GetEventLogMessageText removed from Read
  method.
- GetMessageText function and variable added
- Message field supported by previous version now only
  available either by setting $Win32::EventLog::GetMessageText=1
  or calling Win32::EventLog::GetMessageText function.
- Some documentation added.

## 0.05 [1998-11-14]

- support 'User' and 'Message' fields (suggested by
  Martin Pauley)

## 0.04 [1998-09-07]

- grow buffer for ReadEventLog() as needed

## 0.03 [1998-02-06]

- Fix Read(...,\%foo)

## 0.02 [1997-12-04]

- Open() method has been renamed to new()
- Perl code is cleaner
- cosmetic tweaks

## 0.01 [1997-04-05]

- original version; created by h2xs 1.18
- imported from Actiware version

