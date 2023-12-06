Group Policy Objects are how Windows Server and [[MS active directory]] enables the administrator(s) to enact policies on users, organizational units, groups, or objects.

A group policy object can be configured in the Group Policy Management application. 

The *scope* of a GPO determines what objects, subjects, and/or groups are effected by the policy. 


Each GPO has a user and a computer component
	Each component has settings specific to that resource
	User/computer/both can be set. User policies are applied when a user logs in, computer policies are applied when the computer boots up.

Inheritance webs can get kind of complex with GPOs and can often cause conflicts
	Local policies are executed first, then sites, then domains, then OUs. Generally, this is also the order of authority for disputing rule conflicts.
	A few instances:
		If a parent GPO has a setting configured and a child GPO does not have a setting configured, the child inherits the parent's GPO in full
		If a parent GPO has a policy conflicting with the child GPO, the child overwrites the inherited value and applies its own setting
		The administrator can manually control how inheritance is applied, regardless of whether or not there's conflicts
	A policy being "Enabled" means that its settings will apply to all objects and subjects in the groups its linked to
	A policy being "Enforced" means that the policy cannot be overwritten by other policies that apply later, even if inheritance is blocked
	