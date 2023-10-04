@startuml

:User: as User

rectangle SERVERLESS {

	(Create function) as Create
	(Delete function) as Delete
	(Edit function) as Edit
	(Publish function) as Publish
	(Unpublish function) as Unpublish
	(View function log) as ViewLog

	(Edit information) as EditInfo
	(Edit code) as EditCode
	(Edit name) as EditName
	(Edit description) as EditDesc
	(Edit tags) as EditTags
	(Edit arguments) as EditArgs
	(Edit triggers) as EditTrig

	(View running time) as ViewTime
	(View message) as ViewMsg

	note right of Create
		Described in great details in
		"Create function Use Case"
	end note

	Edit <.. EditInfo : <<extend>>
	Edit <.. EditCode : <<extend>>
	EditInfo <.. EditName : <<extend>>
	EditInfo <.. EditDesc : <<extend>>
	EditInfo <.. EditTags : <<extend>>
	EditCode <.. EditArgs  : <<extend>>
	EditCode <.. EditTrig : <<extend>>

	ViewLog <.. ViewTime : <<extend>>
	ViewLog <.. ViewMsg : <<extend>>
}

left to right direction
User --> Create
User --> Delete
User --> Edit
User --> Publish
User --> Unpublish
User --> ViewLog

@enduml