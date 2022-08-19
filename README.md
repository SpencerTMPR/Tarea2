//# Tarea2
//Edgard Spencer Velez Giron #20191033060

//"Una radio de Tegucigalpa desea presentar a su publico una encuesta en la cual quiere saber si el publico esta de acuerdo con el top 50 de canciones que se encuentra en Spotify, queriendo
//saber si en verdad en Honduras estas serian las canciones mas sonadas y buscadas,  por lo que se hara un algoritmo el cual recapitule las 25 canciones mas
//votadas por el publico y de esta manera pueda ordenar las canciones desde la cancion mas sonada que seria la cancion del top 1, hasta la menos escuchada que seria el top 25 creando asi una
//lista definitiva la cual presentara las 25 canciones mas sonadas en la radio"

package main

import pqueue "github.com/nu7hatch/gopqueue"

type Task struct {
	Name     string
	priority int
}

func (t *Task) Less(other interface{}) bool {
	return t.priority < other.(*Task).priority
}

func main() {
	q := pqueue.New(0)
	q.Enqueue(&Task{"Enseñame a Bailar-Bad Bunny", 22})
	q.Enqueue(&Task{"Normal-Feid", 15})
	q.Enqueue(&Task{"Dakiti-Bad Bunny", 19})
	q.Enqueue(&Task{"Despecha-Rosalia", 7})
	q.Enqueue(&Task{"Neverita-Bad Bunny", 11})
	q.Enqueue(&Task{"La Bachata-Manuel Turizo", 7})
	q.Enqueue(&Task{"Me Fui de Vacaciones-Rosalia", 20})
	q.Enqueue(&Task{"Como dormiste-Rels B", 4})
	q.Enqueue(&Task{"Me Fui de Vacaciones-Rosalia", 17})
	q.Enqueue(&Task{"Te Felicito-Shakira Feat. Rauw Alejandro", 8})
	q.Enqueue(&Task{"X ultima vez-Daddy Yankee Feat Bad Bunny", 24})
	q.Enqueue(&Task{"Efecto-Bad Bunny", 1})
	q.Enqueue(&Task{"Moscow Mule-Bad Bunny", 6})
	q.Enqueue(&Task{"As It Was-Harry Styles", 25})
	q.Enqueue(&Task{"La Llevo al Cielo-Anuel Feat. Ñengo Flow & Chencho Corleone", 21})
	q.Enqueue(&Task{"Dos mil 16-Bad Bunny", 18})
	q.Enqueue(&Task{"Music Session: Quevedo-Bizarrap Feat. Quevedo", 3})
	q.Enqueue(&Task{"Provenza-Karol G", 13})
	q.Enqueue(&Task{"Titi me pregunto-Bad Bunny", 4})
	q.Enqueue(&Task{"Me porto bonito-Bad Bunny", 2})
	q.Enqueue(&Task{"Otro atardecer-Bad Bunny", 23})
	q.Enqueue(&Task{"Ojitos Lindos-Bad Bunny Feat. Bomba Estereo", 5})
	q.Enqueue(&Task{"Party-Bad Bunny Feat. Rauw Alejandro", 9})
	q.Enqueue(&Task{"Un coco-Bad Bunny", 12})
	q.Enqueue(&Task{"La corriente-Bad Bunny Feat. Tony Dize", 10})
	q.Enqueue(&Task{"Un ratito-Bad Bunny", 14})

	println("El top 25 de Honduras seria: ")
	println(" ")

	for i := 0; i < 25; i += 1 {
		task := q.Dequeue()
		print(i + 1)
		print("-")
		println(task.(*Task).Name)
	}
}
