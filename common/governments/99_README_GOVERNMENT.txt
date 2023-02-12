# Government Requirements
# -----------------------
#
# Government authorities and civics use a custom list syntax instead of normal
# triggers in potential and possible to specify valid combinations:
#
#
#	possible = {
#
#		ethics = {
#			# All of these are required:
#			value = ethic_1
#			value = ethic_2
#
#			# One of these is required:
#			OR = {
#				text = translation_key		# optional, overrides the auto-generated tooltip text
#				value = ethic_3
#				value = ethic_4
#			}
#
#			# This one must not be present:
#			NOT = {
#				text = translation_key		# optional
#				value = ethic_5
#				# May contain only one value!
#			}
#
#			# None of these must be present:
#			NOR = {
#				text = translation_key		# optional
#				value = ethic_6
#				value = ethic_7
#			}
#		}
#
#		country_type = { ... }
#
#		authority = { ... }
#
#		civics = { ... }
#
#		# Outer scope is implicitly AND, which means that the result from all specified ethics, country_type, authority or civics blocks must be true
#		# However, it's also possible to add inner OR or AND blocks:
#		OR = {
#			# Only one of these need to be present:
#			authority = { value = my_authority }
#			civics = { value = my_civic }
#
#			# OR/AND blocks can be nested. In this case, that means that if the AND block is fulfilled, the outer OR block will also be fulfilled,
#			# since the OR block only requires one of its constituents to be fulfilled
#			AND = {
#				ethics = { value = ethic_1 }
#				civics = { my_other_civic }
#			}
#		}
#
#		text = translation_key				# optional
#	}
#
#
# Authorities support:
#	- country_type
#	- ethics
#
# Civics support:
#	- country_type
#	- ethics
#	- authority
#	- civics
#
# Species classes support:
#	- country_type
#	- ethics
#	- authority
#	- civics
#