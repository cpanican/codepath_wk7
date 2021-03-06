# Project 7 - WordPress Pentesting

Time spent: **7** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Unauthenticated Stored Cross-Site Scripting (XSS)
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [X] GIF Walkthrough:
    ![xss](./gifs/1_xss.gif)
  - [X] Steps to recreate: 
    1. Post the following text to a comment: [Link 1](./assets/1_xss.txt)
    2. When an admin sees/approves the comment, then the code is executed.
  - [X] Affected source code:
    - [Link 1](https://wpvulndb.com/vulnerabilities/7945)
    - [Link 2](https://www.exploit-db.com/exploits/36844/)
    - [Link 3](http://klikki.fi/adv/wordpress2.html)
    - [Link 4](http://packetstormsecurity.com/files/131644/)
2. (Required) Authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds.
  - [X] Summary: 
    - Vulnerability types: CSRF
    - Tested in version: 4.2
    - Fixed in version: 4.7.3
  - [X] GIF Walkthrough: 
    ![csrf](./gifs/2_csrf.gif)
  - [X] Steps to recreate: 
    1. As an Author/Contributor, post this YouTube embed snippet:
    ```
    [embed src='https://www.youtube.com/embed/dQw4w9WgXcQ\x3csvg onload=alert(document.cookie)\x3e'][/embed]
    ```
  - [X] Affected source code:
    - [Link 1](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6817)
    - [Link 2](https://nvd.nist.gov/vuln/detail/CVE-2017-6817)
    - [Link 3](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
3. (Required) Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [X] GIF Walkthrough:
    ![xss](./gifs/3_xss.gif)
  - [X] Steps to recreate: 
    1. Upload a media file and add a code snippet like this to the file name:
    ```
    <img src=a onClick=alert(document.cookie)>
    ```
    2. Upload as an attachment and post it.
    3. NOTE: You need higher posting permissions to upload pictures
  - [X] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/c9e60dab176635d4bfaaf431c0ea891e4726d6e0)
4. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
5. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:

## Assets

List any additional assets, such as scripts or files

- [XSS Comment](./assets/1_xss.txt)
- [Pusheen](./assets/)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

1. The command `root@kali:~# wpscan --url http://wpdistillery.vm --random-agent` returned
`Scan Aborted: invalid option: --random-agent`
2. Windows does not allow some special characters in file names such as `/`, `|`, `(`, `)` etc.

## License

    Copyright [2018] [Chris Panican]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
