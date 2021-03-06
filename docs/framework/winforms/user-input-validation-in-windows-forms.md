---
title: Validação da entrada do usuário no Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, validating user input
- validation [Windows Forms], Windows Forms user input
- user input [Windows Forms], validating in Windows Forms
- validating user input [Windows Forms], Windows Forms
ms.assetid: 4ec07681-1dee-4bf9-be5e-718f635a33a1
ms.openlocfilehash: 87124438118f05d426d5a33c914634922e657c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498902"
---
# <a name="user-input-validation-in-windows-forms"></a>Validação da entrada do usuário no Windows Forms
Quando os usuários inserem dados em seu aplicativo, convém verificar se os dados são válidos antes de seu aplicativo utilizá-los. Você pode exigir que determinados campos de texto não sejam de comprimento zero, que um campo seja formatado como um número de telefone ou outros tipos de dados bem formados ou que uma cadeia de caracteres não contenha caracteres desprotegidos que poderiam ser usados para comprometer a segurança de um banco de dados. O Windows Forms fornece várias maneiras para validar a entrada em seu aplicativo.  
  
## <a name="validation-with-the-maskedtextbox-control"></a>Validação com o controle MaskedTextBox  
 Se você precisar que os usuários insiram dados em um formato bem definido, como um número de telefone ou um número de peça, você pode fazer isso rapidamente e com o mínimo de código usando o <xref:System.Windows.Forms.MaskedTextBox> controle. Uma *máscara* é uma cadeia de caracteres composta de caracteres de uma linguagem de mascaramento que especifica quais caracteres podem ser inseridos em qualquer posição determinada de uma caixa de texto. O controle exibe um conjunto de avisos para o usuário. Se o usuário digita uma entrada incorreta, como digitar uma letra quando é necessário um dígito, o controle rejeitará automaticamente a entrada.  
  
 A linguagem de mascaramento que é usada pelo <xref:System.Windows.Forms.MaskedTextBox> é muito flexível. Ela permite que você especifique os caracteres exigidos, caracteres opcionais, caracteres literais como hifens e parênteses, caracteres de moeda e separadores de data. O controle também funciona bem quando associado a uma fonte de dados. O <xref:System.Windows.Forms.Binding.Format> evento em uma associação de dados pode ser usado para reformatar os dados de entrada para estar de acordo com a máscara e o <xref:System.Windows.Forms.Binding.Parse> evento pode ser usado para reformatar os dados de saída para estar em conformidade com as especificações do campo de dados.  
  
 Para obter mais informações, consulte [Controle MaskedTextBox](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md).  
  
## <a name="event-driven-validation"></a>Validação controlada por evento  
 Se você deseja ter controle total programático sobre a validação ou precisa realizar validações complexas, é necessário usar os eventos de validação incorporados à maioria dos controles dos Windows Forms. Cada controle que aceita entrada do usuário de forma livre tem um <xref:System.Windows.Forms.Control.Validating> evento que ocorrerá sempre que o controle requer a validação de dados. No <xref:System.Windows.Forms.Control.Validating> método do manipulador de eventos, você pode validar a entrada do usuário de várias maneiras. Por exemplo, se você tiver uma caixa de texto que deve conter um código postal, poderá realizar a validação das seguintes maneiras:  
  
-   Se o código postal deve pertencer a um grupo específico de códigos postais, você pode realizar uma comparação de cadeia de caracteres na entrada para validar os dados inseridos pelo usuário. Por exemplo, se o código postal deve estar no conjunto {10001, 10002, 10003}, você pode usar uma comparação de cadeia de caracteres para validar os dados.  
  
-   Se o código postal deve estar em uma forma específica, você pode usar expressões regulares para validar os dados inseridos pelo usuário. Por exemplo, para validar a forma `#####` ou `#####-####`, você pode usar a expressão regular `^(\d{5})(-\d{4})?$`. Para validar a forma `A#A #A#`, você pode usar a expressão regular `[A-Z]\d[A-Z] \d[A-Z]\d`. Para obter mais informações sobre expressões regulares, consulte [Expressões regulares do .NET Framework](../../../docs/standard/base-types/regular-expressions.md) e [Exemplos de expressão regular](../../../docs/standard/base-types/regular-expression-examples.md).  
  
-   Se o código postal deve ser um CEP válido dos Estados Unidos, você poderia chamar um serviço Web de código postal para validar os dados inseridos pelo usuário.  
  
 O <xref:System.Windows.Forms.Control.Validating> evento é fornecido um objeto do tipo <xref:System.ComponentModel.CancelEventArgs>. Se você determinar que os dados do controle não são válidos, você pode cancelar a <xref:System.Windows.Forms.Control.Validating> evento definindo esse objeto <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propriedade `true`. Se você não definir a <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propriedade, Windows Forms assumirá que a validação foi bem-sucedida para o controle e gerar o <xref:System.Windows.Forms.Control.Validated> eventos.  
  
 Para obter um exemplo de código que valida um endereço de email em um <xref:System.Windows.Controls.TextBox>, consulte <xref:System.Windows.Forms.Control.Validating>.  
  
### <a name="data-binding-and-event-driven-validation"></a>Vinculação de dados e validação controlada por evento  
 A validação é muito útil quando você tiver associado seus controles a uma fonte de dados, como uma tabela de banco de dados. Ao usar a validação, você pode verificar se os dados do seu controle satisfazem o formato exigido pela fonte de dados e, se eles não contêm caracteres especiais, como aspas e barras invertidas, que podem não ser seguros.  
  
 Quando você usa a associação de dados, os dados em seu controle são sincronizados com a fonte de dados durante a execução do <xref:System.Windows.Forms.Control.Validating> eventos. Se você cancelar o <xref:System.Windows.Forms.Control.Validating> evento, os dados não serão sincronizados com a fonte de dados.  
  
> [!IMPORTANT]
>  Se você tiver uma validação personalizada depois que o <xref:System.Windows.Forms.Control.Validating> evento, ele não afetará a vinculação de dados. Por exemplo, se você tiver código em um <xref:System.Windows.Forms.Control.Validated> evento que tenta cancelar a associação de dados, a ligação de dados ainda ocorrerá. Nesse caso, para executar a validação na <xref:System.Windows.Forms.Control.Validated> evento, o controle de alterações **modo de atualização de fonte de dados** propriedade (**em (Databindings)**\\ **(Avançado)** ) da **OnValidation** à **nunca**e adicione *controle*`.DataBindings["`*\<YOURFIELD >*  `"].WriteValue()` ao seu código de validação.  
  
### <a name="implicit-and-explicit-validation"></a>Validação explícita e implícita  
 Então quando os dados de um controle são validados? Isso cabe a você, o desenvolvedor. Você pode usar a validação implícita ou explícita, dependendo das necessidades do seu aplicativo.  
  
#### <a name="implicit-validation"></a>Validação implícita  
 A abordagem de validação implícita valida os dados enquanto o usuário os digita. Você pode validar os dados conforme eles são inseridos em um controle através da leitura das teclas enquanto elas são pressionadas ou, mais comumente, sempre que o usuário retirar o foco de entrada de um controle e movê-lo para o próximo. Essa abordagem é útil quando você deseja fornecer comentários imediatos sobre os dados, enquanto os usuários trabalham.  
  
 Se você quiser usar a validação implícita para um controle, você deve definir que controlam <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propriedade para `true`. Se você cancelar a <xref:System.Windows.Forms.Control.Validating> evento, o comportamento do controle será determinado pelo valor que você atribuiu ao <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A>. Se você atribuiu <xref:System.Windows.Forms.AutoValidate.EnablePreventFocusChange>, o cancelamento do evento fará com que o <xref:System.Windows.Forms.Control.Validated> evento não ocorra. O foco de entrada permanecerá no controle atual até que o usuário altere os dados para uma entrada válida. Se você atribuiu <xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>, o <xref:System.Windows.Forms.Control.Validated> evento não ocorrerá quando você cancelar o evento, mas o foco ainda passará para o próximo controle.  
  
 Atribuindo <xref:System.Windows.Forms.AutoValidate.Disable> para o <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propriedade impede que a validação implícita completamente. Para validar seus controles, você precisará usar a validação explícita.  
  
#### <a name="explicit-validation"></a>Validação explícita  
 A abordagem de validação explícita valida os dados de uma só vez. Você pode validar os dados em resposta a uma ação do usuário, como clicar em um botão Salvar ou um link Avançar. Quando a ação do usuário ocorre, você pode disparar a validação explícita de uma das seguintes maneiras:  
  
-   Chamar <xref:System.Windows.Forms.ContainerControl.Validate%2A> para validar o último controle que tenha perdido o foco.  
  
-   Chamar <xref:System.Windows.Forms.ContainerControl.ValidateChildren%2A> para validar todos os controles filho em um controle de formulário ou contêiner.  
  
-   Chamar um método personalizado para validar manualmente os dados nos controles.  
  
#### <a name="default-implicit-validation-behavior-for-windows-forms-controls"></a>Comportamento de validação implícita padrão de controles dos Windows Forms  
 Controles de formulários do Windows diferentes têm diferentes padrões de seus <xref:System.Windows.Forms.ContainerControl.AutoValidate%2A> propriedade. A tabela a seguir mostra os controles mais comuns e seus valores padrão.  
  
|Controle|Comportamento de validação padrão|  
|-------------|---------------------------------|  
|<xref:System.Windows.Forms.ContainerControl>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
|<xref:System.Windows.Forms.PropertyGrid>|Propriedade não exposta no Visual Studio|  
|<xref:System.Windows.Forms.ToolStripContainer>|Propriedade não exposta no Visual Studio|  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Forms.AutoValidate.Inherit>|  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Forms.AutoValidate.EnableAllowFocusChange>|  
  
## <a name="closing-the-form-and-overriding-validation"></a>Fechar o formulário e substituir a validação  
 Quando um controle mantém o foco porque os dados que ele contém são inválidos, é impossível fechar o formulário pai através das maneiras comuns:  
  
-   Clicando no botão **Fechar**.  
  
-   Selecionando **Fechar** no menu **Sistema**.  
  
-   Chamando o <xref:System.Windows.Forms.Form.Close%2A> método programaticamente.  
  
 No entanto, em alguns casos, você talvez queira permitir que o usuário feche o formulário independentemente se os valores nos controles são válidos. Você pode substituir a validação e fechar um formulário que ainda contém dados inválidos, criando um manipulador para o formulário <xref:System.Windows.Forms.Form.Closing> eventos. No evento, defina a <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> propriedade para `false`. Isso força o formulário a fechar. Para obter mais informações e um exemplo, consulte <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Se você forçar o formulário a fechar desta maneira, todos os dados nos controles do formulário que ainda não tiverem sido salvos serão perdidos. Além disso, os formulários modais não validam o conteúdo dos controles quando eles são fechados. Você ainda pode usar a validação de controle para bloquear o foco em um controle, mas você não precisa se preocupar com o comportamento associado ao fechamento do formulário.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.Control.Validating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>
- <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType>
- [Controle MaskedTextBox](../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
- [Exemplos de expressões regulares](../../../docs/standard/base-types/regular-expression-examples.md)
