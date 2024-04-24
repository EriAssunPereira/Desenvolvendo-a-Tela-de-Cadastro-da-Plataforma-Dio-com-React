# Desenvolvendo-a-Tela-de-Cadastro-da-Plataforma-Dio-com-React

Desenvolvendo a tela de cadastro da plataforma Dio com React! Vamos passar por algumas etapas que podem nos ajudar a construir essa tela:

1. **Estruture o componente de cadastro**:
   Crie um novo componente React para a tela de cadastro. Este componente será responsável por renderizar o formulário e lidar com o estado dos dados inseridos pelo usuário.

   ```javascript
   import React, { useState } from 'react';
   import styled from 'styled-components';

   const FormContainer = styled.div`
     /* Adicione estilos aqui */
   `;

   const RegistrationForm = () => {
     const [formData, setFormData] = useState({
       nome: '',
       email: '',
       senha: '',
     });

     // Funções para lidar com as mudanças no formulário e submissão irão aqui

     return (
       <FormContainer>
         {/* Formulário de cadastro irá aqui */}
       </FormContainer>
     );
   };

   export default RegistrationForm;
   ```

2. **Crie campos de formulário com styled-components**:
   Utilize `styled-components` para estilizar os campos do formulário. Isso permite que você aplique estilos diretamente nos componentes sem se preocupar com conflitos de classes CSS.

   ```javascript
   const Input = styled.input`
     /* Adicione estilos para o input aqui */
   `;

   const Button = styled.button`
     /* Adicione estilos para o botão aqui */
   `;
   ```

3. **Implemente os Hooks para gerenciar o estado**:
   Use o Hook `useState` para criar um estado para cada campo do formulário. O Hook `useEffect` pode ser útil se você precisar realizar alguma ação quando o estado mudar.

4. **Adicione validação de formulário**:
   Antes de enviar os dados, é importante validar os campos para garantir que os dados estão corretos. Você pode criar funções de validação que são chamadas quando o formulário é submetido.

5. **Envie os dados do formulário**:
   Quando o usuário submeter o formulário, você deve coletar os dados do estado e enviá-los para o servidor ou API correspondente.

6. **Feedback visual para o usuário**:
   Forneça feedback para o usuário após a submissão do formulário, como mensagens de erro ou confirmação de cadastro bem-sucedido.

Aqui está um exemplo de como o formulário de cadastro pode ser implementado:

```javascript
// ...imports e estilos

const RegistrationForm = () => {
  const [formData, setFormData] = useState({
    nome: '',
    email: '',
    senha: '',
  });

  const handleChange = (event) => {
    const { name, value } = event.target;
    setFormData(prevState => ({
      ...prevState,
      [name]: value,
    }));
  };

  const handleSubmit = (event) => {
    event.preventDefault();
    // Validação e envio dos dados
    console.log(formData);
  };

  return (
    <FormContainer>
      <form onSubmit={handleSubmit}>
        <Input
          type="text"
          name="nome"
          placeholder="Nome completo"
          value={formData.nome}
          onChange={handleChange}
        />
        <Input
          type="email"
          name="email"
          placeholder="E-mail"
          value={formData.email}
          onChange={handleChange}
        />
        <Input
          type="password"
          name="senha"
          placeholder="Senha"
          value={formData.senha}
          onChange={handleChange}
        />
        <Button type="submit">Cadastrar</Button>
      </form>
    </FormContainer>
  );
};

export default RegistrationForm;
```

Lembre-se de substituir o `console.log` pela lógica de envio dos dados para o servidor. E não se esqueça de testar cada parte do seu código para garantir que tudo está funcionando como esperado. Se precisar de mais ajuda ou tiver dúvidas, estou aqui para auxiliar. 

https://github.com/digitalinnovationone/trilha-react-desafio-3

https://www.figma.com/file/fvjQQNtqaUdpuNixvCZVav/DIO-CLONE?node-id=0%3A1
