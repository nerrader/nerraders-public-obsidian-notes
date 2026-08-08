---
subjects: Licenses
status: done
---
 **Open source licenses** are legal documents that grant users the right to use, modify, and share software code, which is otherwise restricted by default copyright laws.

Choosing a license is practically necessary because **omitting one legally prevents others from using or modifying your code**, while selecting an incompatible license can create compliance risks or force you to open-source your entire project if you use strong copyleft dependencies.

For open source projects, you will usually come across licenses that fall into these two categories:

### Permissive Licenses

Permissive licenses are designed to provide maximum freedom to use, distribute, or modify software with minimal restrictions.

- Examples: [[MIT License]], [[Apache License 2.0]]
  These licenses are best for libraries and tools meant for wide adoption for everyone to use.

### Copyleft Licenses

Copyleft licenses are designed that you can use, modify, or distribute the code, but you must make the project open source, or give the source code to the original author.

- **Examples:** [[GPL v3.0]], [[AGPL v3.0]], LGPL.
  These licenses are best for projects where the author wants to ensure the community’s contributions benefit everyone equally. However, these types of licenses usually mean that the project does get less popularity sometimes.

> [!IMPORTANT] Add Headers for Copyleft Files
> 
> If you are using a license like the ones mentioned above, it is good practice to add a header to each one of your source code files.
> 
> For example, the license header for AGPL licensed code is:
> 
> <one line to give the program's name and a brief idea of what it does.
> Copyright (C) {year} {name of author}
> This program is free software: you can redistribute it and/or modify it under the terms of the
> GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
> 
> This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY;
> without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
> PURPOSE.
> 
 See the GNU Affero General Public License for more details.
> You should have received a copy of the GNU Affero General Public License along with this
> program. If not, see <https://www.gnu.org/licenses/>.


