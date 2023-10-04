@startuml

:User: as User

rectangle SERVERLESS {

    (Create function) as Create
	(Write function code) as Write
	(Upload file with code) as Upload
	(Select available triggers) as SelectTrig
	(Set function name) as SetName
	(Set function description) as SetDesc << Optional >>
	(Set function tags) as SetTags << Optional >>
	(Run function in test mode) as Test << Optional >>
	(Add function arguments) as AddArgs << Optional >>
	(Press "Create" button) as CreateBtn
	(Select programming language) as SelectLang
	(Sign in) as SignIn
	
	note right of Write
		Code editing is unavailable 
		for <i>wasm</i> files
	end note

	note left of CreateBtn
		Only registered users 
		can save functions
	end note
	
	Write <.. Create : <<include>>
	Upload .left.> Create : <<extend>>
	SetName <.. Create : <<include>>
	Create ..> SetDesc : <<include>>
	Create ..> SetTags : <<include>>
	SelectTrig <.. Create : <<include>>
	Create ..> Test : <<include>>
	Create ..> AddArgs : <<include>>
	Create .left.> CreateBtn : <<include>>
	SelectLang <.. Create : <<include>>
}

left to right direction
User --> Create
User --> SignIn

@enduml
