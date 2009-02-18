# vim:set ts=4
#
# ibus-table-erbi - The ErBi for IBus Tables.
#
# Copyright (c) 2008-2009 Yu Yuwei <acevery@gmail.com>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.
#
# $Id: $
#

createdb = \
	$(IBUS_TABLE_CREATEDB) 

if IBUS_TABLE_EXTRA_PHRASES
createdb += -e @IBUS_TABLE_EXTRAPHRASE@
endif

tables_DATA =
engine_DATA =

if IBUS_TABLE_BUILD_ERBI_QS
tables_DATA += erbi_qs.db
engine_DATA += erbi_qs.engine
endif

tables_DATA += $(NULL)
engine_DATA += $(NULL)

tablesdir = $(datadir)/ibus-table/tables
enginedir = $(datadir)/ibus/engine

EXTRA_DIST = \
	erbi_qs.txt \
	$(NULL)

DISTCLEANFILES = \
	*.db \
	*.engine \
	$(NULL)

.db.engine:
	@echo "$@ is done:)"

.txt.db:
	$(createdb) -n $@ -s $<

