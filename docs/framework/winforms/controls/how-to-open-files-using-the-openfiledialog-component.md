---
title: 'Como: Abrir arquivos usando o componente OpenFileDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 87e7640da76205341b9e95310314800ac9dbfe30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678805"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>Como: Abrir arquivos usando o componente OpenFileDialog
O <xref:System.Windows.Forms.OpenFileDialog> componente permite que os usuários pesquisem as pastas do seu computador ou em qualquer computador na rede e selecione um ou mais arquivos para abrir. A caixa de diálogo retorna o caminho e o nome do arquivo que o usuário selecionou na caixa de diálogo.  
  
 Depois que o usuário tiver selecionado o arquivo a ser aberto, há duas abordagens para o mecanismo de abertura do arquivo. Se você preferir trabalhar com fluxos de arquivos, você pode criar uma instância da <xref:System.IO.StreamReader> classe. Como alternativa, você pode usar o <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir o arquivo selecionado.  
  
 O primeiro exemplo a seguir envolve uma <xref:System.Security.Permissions.FileIOPermission> verificação de permissão (conforme descrito na "Observação de segurança" abaixo), mas fornece a você acesso ao nome do arquivo. É possível usar essa técnica do Computador Local, da Intranet e zonas da Internet. O segundo método também faz um <xref:System.Security.Permissions.FileIOPermission> verificação de permissão, mas é mais adequado para aplicativos nas zonas da Intranet ou Internet.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>Abrir um arquivo como um fluxo usando o componente OpenFileDialog  
  
1.  Exiba a caixa de diálogo **Abrir Arquivo** e chame um método para abrir o arquivo selecionado pelo usuário.  
  
     Uma abordagem é usar o <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para exibir a caixa de diálogo Abrir arquivo e usar uma instância da <xref:System.IO.StreamReader> classe para abrir o arquivo.  
  
     O exemplo a seguir usa o <xref:System.Windows.Forms.Button> do controle <xref:System.Windows.Forms.Control.Click> manipulador de eventos para abrir uma instância da <xref:System.Windows.Forms.OpenFileDialog> componente. Quando um arquivo é escolhido e o usuário clica em **OK**, o arquivo selecionado na caixa de diálogo será aberto. Nesse caso, os conteúdos serão exibidos em uma caixa de mensagem, apenas para mostrar que o fluxo de arquivo foi lido.  
  
    > [!IMPORTANT]
    >  Para obter ou definir a <xref:System.Windows.Forms.FileDialog.FileName%2A> propriedade, seu assembly requer um nível de privilégio concedido pela <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Se você estiver executando em um contexto de confiança parcial, o processo poderá gerar uma exceção em razão dos privilégios insuficientes. Para obter mais informações, consulte [Noções Básicas da Segurança de Acesso do Código](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     O exemplo supõe que seu formulário tem um <xref:System.Windows.Forms.Button> controle e um <xref:System.Windows.Forms.OpenFileDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Para obter mais informações sobre a leitura de fluxos de arquivos, consulte <xref:System.IO.FileStream.BeginRead%2A> e <xref:System.IO.FileStream.Read%2A>.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>Abrir um arquivo como um arquivo usando o componente OpenFileDialog  
  
1.  Use o <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para exibir a caixa de diálogo e o <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir o arquivo.  
  
     O <xref:System.Windows.Forms.OpenFileDialog> do componente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método retorna os bytes que compõem o arquivo. Esses bytes oferecem um fluxo de leitura. No exemplo a seguir, uma <xref:System.Windows.Forms.OpenFileDialog> componente é instanciado com um filtro de "cursor", permitindo que o usuário escolher somente arquivos com a extensão de nome de arquivo`.cur`. Se um arquivo `.cur` for escolhido, o cursor do formulário será definido como o cursor selecionado.  
  
    > [!IMPORTANT]
    >  Para chamar o <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método, seu assembly requer um nível de privilégio concedido pela <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe. Se você estiver executando em um contexto de confiança parcial, o processo poderá gerar uma exceção em razão dos privilégios insuficientes. Para obter mais informações, consulte [Noções Básicas da Segurança de Acesso do Código](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     O exemplo supõe que seu formulário tem um <xref:System.Windows.Forms.Button> controle.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.OpenFileDialog>
- [Componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
