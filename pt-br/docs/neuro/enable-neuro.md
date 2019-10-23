Title: Ativar o Neuro

# Ativar o Neuro

Para a integração CITSmart/Neuro funcionar, você deve:

- Ter a versão 8.0.0.0 ou superior da CITSmart
- Ter o CITSmart configurado para acesso HTTPS: //
- Ter os parâmetros de integração configurados no CITSmart


![Neuro Conection][1]

- **Parâmetro 309:**

    ```sh
    Value: Yes
    ```

- **Parâmetro 310:**

    ```sh
    https://localhost:8443/cit-esi-web
    ```

- **Parâmetro 311:**

    ```sh
    citsmart.local\neuro.user
    ```
    

!!! success "USUÁRIO NEURO"
    Para que a integração funcione corretamente é necessário que o usuário de serviço criado para o Neuro contenha no campo login o atributo de identificação do domínio, ou seja, "citsmart.local" (ex. O usuário "Neuro" deverá ter no campo login a seguinte informação  "citsmart.local\neuro.user").


[1]:images/neuro-conection.png
