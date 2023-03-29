package main

import (
	"fmt"
	"net"
	"net/http"
)

func main() {
	urls := []string{"https://www.google.com", "https://www.test-site-123.com", "https://www.hotmail.com", "https://www.mercadolivre.com.br"}

	for indice, endpoint := range urls {
		response, err := http.Get(endpoint)
		if err != nil {
			fmt.Printf("A URL n%v nao existe\n", indice+1)
			//fmt.Println(err)
			continue

		}
		//defer response.Body.Close()

		if response.StatusCode == http.StatusOK {
			fmt.Printf("A URL n%v existe\n", indice+1)
		}

	}
	fmt.Println()

	for _, url := range urls {
		urlFatiado := url[8:]
		ips, err := net.LookupIP(urlFatiado)
		if err != nil {
			fmt.Printf("Erro ao resolver o endereço IP da URL %s \n", urlFatiado)
			fmt.Println(err)
			fmt.Println()
			continue
		}

		for _, ip := range ips {
			fmt.Printf("%s: %s\n", url, ip)
		}
		fmt.Println()

	}

}
