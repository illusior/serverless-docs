@startuml

:User: as User
:User Not Programmer: as UserNot

rectangle SERVERLESS {

	(Bind function to trigger) as Bind
	(Edit binding) as Edit
	
	(Select trigger) as SelectTrig
	(Select function) as SelectFun
	(Set trigger arguments) as SetTrigArgs
	(Set function arguments) as SetFunArgs
	
	Bind <.. SelectTrig : <<include>>
	Bind <.. SelectFun : <<include>>
	SelectTrig <.. SetTrigArgs : <<include>>
	SelectFun <.. SetFunArgs : <<include>>
	
	Edit <.. SetTrigArgs : <<include>>
	Edit <.. SetFunArgs : <<include>>
}

User --> Bind
User --> Edit

UserNot --> Bind
UserNot --> Edit

@enduml
