---
title: Visão geral da biblioteca de classes do .NET
ms.date: 02/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], library overview
- classes [.NET Core], library overview
- .NET, library overview
- class objects value type
- naming conventions [.NET Framework]
- types, .NET Framework
- user-defined types
- Visual Basic, data types
- data types [.NET Framework], C++
- Visual C#, data types
- libraries, .NET Framework class library
- data types [.NET Framework], F#
- System namespace
- F#, data types
- .NET Framework, class library
- type system [.NET Framework]
- data types [.NET Framework]
- value types
- data types [.NET Framework], Visual Basic
- Common Language Specification
- namespaces [.NET Framework]
- floating point value type
- class library [.NET Framework]
- CLS
- logical value type
- .NET Framework class library, about
- built-in types
- namespaces [.NET Framework], about namespaces
- Visual C++, data types
- members [.NET Framework], type
- data types [.NET Framework], C#
- integer value type
- base types, class library
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b00d08f43874518e117739d4a9502bf9463db5c1
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029864"
---
# <a name="net-class-library-overview"></a>Visão geral da biblioteca de classes do .NET

As implementações do .NET incluem classes, interfaces, delegados e tipos de valor que agilizam e otimizam o processo de desenvolvimento e dão acesso à funcionalidade do sistema. Para facilitar a interoperabilidade entre linguagens, os tipos do .NET têm conformidade com CLS e, assim, podem ser usados por qualquer linguagem de programação cujo compilador esteja de acordo com a CLS (Common Language Specification).  
  
 Os tipos do .NET são a base na qual os aplicativos, os componentes e os controles do .NET são criados. As implementações do .NET incluem tipos que realizam as seguintes funções:  
  
-   Representam tipos de dados base e exceções.  
  
-   Encapsulam estruturas de dados.  
  
-   Executam E/S.  
  
-   Acessam informações sobre tipos carregados.  
  
-   Invocam verificações de segurança do .NET Framework.  
  
-   Fornecem acesso a dados, uma GUI detalhada do lado do cliente e uma GUI do lado do cliente controlada pelo servidor.  
  
 O .NET fornece um conjunto avançado de interfaces, bem como classes abstratas e concretas (não abstratas). Você pode usar as classes concretas como estão ou, em muitos casos, pode derivar suas próprias classes a partir delas. Para usar a funcionalidade de uma interface, você pode criar uma classe que implementa a interface ou derivar uma classe de uma das classes do .NET que implementa a interface.  
  
## <a name="naming-conventions"></a>Convenções de nomenclatura

 Os tipos do .NET usam um esquema de nomenclatura de sintaxe por ponto que denota uma hierarquia. Essa técnica agrupa tipos relacionados em namespaces para que eles possam ser pesquisados e referenciados com mais facilidade. A primeira parte do nome completo — até o ponto mais à direita — é o nome do namespace. A última parte do nome é o nome do tipo. Por exemplo, `System.Collections.Generic.List<T>` representa o tipo `List<T>`, que pertence ao namespace `System.Collections.Generic`. Os tipos em <xref:System.Collections.Generic> podem ser usados para trabalhar com coleções genéricas.  
  
 Esse esquema de nomenclatura facilita para desenvolvedores de bibliotecas estender o [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para criar grupos hierárquicos de tipos e nomeá-los de maneira consistente e informativa. Ele também permite que tipos sejam identificados sem ambiguidades por seu nome completo (ou seja, pelo namespace e pelo nome de tipo), o que impede conflitos de nomes de tipo. Os desenvolvedores de bibliotecas devem usar a seguinte convenção para criar nomes para seus namespaces:  
  
 *CompanyName*.*TechnologyName*  
  
 Por exemplo, o namespace `Microsoft.Word` segue esta diretriz.  
  
 O uso de padrões de nomenclatura para agrupar tipos relacionados em namespaces é uma forma muito útil de compilar e documentar bibliotecas de classes. No entanto, esse esquema de nomenclatura não afeta visibilidade, acesso a membro, herança, segurança ou associação. Um namespace pode ser particionado em vários assemblies e um único assembly pode conter tipos de vários namespaces. O assembly fornece a estrutura formal para criação de versão, implantação, segurança, carregamento e visibilidade no Common Language Runtime.  
  
 Para obter mais informações sobre namespaces e nomes de tipos, consulte [Common Type System](../../docs/standard/base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>namespace System

 O <xref:System> é o namespace raiz para tipos fundamentais no.NET. Esse namespace contém classes que representam os tipos de dados base usados por todos os aplicativos: <xref:System.Object> (a raiz da hierarquia de herança), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> etc. Muitos desses tipos correspondem aos tipos de dados primitivos que sua linguagem de programação usa. Ao gravar códigos usando tipos .NET Framework, você pode usar a palavra-chave correspondente da sua linguagem quando um tipo de dados base do .NET Framework é esperado.  
  
 A tabela a seguir lista os tipos base que o .NET fornece, descreve resumidamente cada tipo e indica o tipo correspondente em Visual Basic, C#, C++ e F#.  
  
|Categoria|Nome da classe|Descrição|Tipo de dados em Visual Basic|Tipo de dados em C#|Tipo de dados de C++/CLI|Tipo de dados de F#|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Inteiro|<xref:System.Byte>|Um inteiro de 8 bits sem sinal.|**Byte**|**byte**|**unsigned char**|**byte**|  
||<xref:System.SByte>|Um inteiro de 8 bits com sinal.<br /><br /> Não compatível com CLS.|**SByte**|**sbyte**|**char**<br /> - ou -<br /> **signed** **char**|**sbyte**|  
||<xref:System.Int16>|Um inteiro de 16 bits com sinal.|**Short**|**short**|**short**|**int16**|  
||<xref:System.Int32>|Um inteiro com sinal de 32 bits.|**Integer**|**int**|**int**<br /><br /> - ou -<br /><br /> **long**|**int**|  
||<xref:System.Int64>|Um inteiro com sinal de 64 bits.|**Long**|**long**|**__int64**|**int64**|  
||<xref:System.UInt16>|Um inteiro de 16 bits sem sinal.<br /><br /> Não compatível com CLS.|**UShort**|**ushort**|**unsigned short**|**uint16**|  
||<xref:System.UInt32>|Um inteiro sem sinal de 32 bits.<br /><br /> Não compatível com CLS.|**UInteger**|**uint**|**unsigned int**<br /> - ou -<br /> **unsigned long**|**uint32**|  
||<xref:System.UInt64>|Um inteiro sem sinal de 64 bits.<br /><br /> Não compatível com CLS.|**ULong**|**ulong**|**unsigned __int64**|**uint64**|  
|Ponto flutuante|<xref:System.Single>|Um número de ponto flutuante de precisão simples (32 bits).|**Simples**|**float**|**float**|**float32**</br> ou</br>**single**|  
||<xref:System.Double>|Um número de ponto flutuante de precisão dupla (64 bits).|**Duplo**|**double**|**double**|**float**</br> ou </br> **double**|  
|Lógico|<xref:System.Boolean>|Um valor booliano (verdadeiro ou falso).|**Booliano**|**bool**|**bool**|**bool**|  
|Outros|<xref:System.Char>|Um caractere Unicode (16 bits).|**Char**|**char**|**wchar_t**|**char**|  
||<xref:System.Decimal>|Um valor decimal (128 bits).|**Decimal**|**decimal**|**Decimal**|**decimal**|  
||<xref:System.IntPtr>|Um inteiro com sinal cujo tamanho dependa da plataforma subjacente (um valor de 32 bits em uma plataforma de 32 bits e um valor de 64 bits em uma plataforma de 64 bits).|**IntPtr**<br /><br /> Nenhum tipo interno.|**IntPtr**<br /><br /> Nenhum tipo interno.|**IntPtr**<br /><br /> Nenhum tipo interno.|**unativeint**|  
||<xref:System.UIntPtr>|Um inteiro sem sinal cujo tamanho dependa da plataforma subjacente (um valor de 32 bits em uma plataforma de 32 bits e um valor de 64 bits em uma plataforma de 64 bits).<br /><br /> Não compatível com CLS.|**UIntPtr**<br /><br /> Nenhum tipo interno.|**UIntPtr**<br /><br /> Nenhum tipo interno.|**UIntPtr**<br /><br /> Nenhum tipo interno.|**unativeint**|  
||<xref:System.Object>|A raiz da hierarquia do objeto.|**Object**|**object**|**Object^**|**obj**|  
||<xref:System.String>|Uma cadeia de caracteres Unicode imutável e de comprimento fixo.|**Cadeia de caracteres**|**string**|**String^**|**string**|  
  
 Além dos tipos de dados base, o namespace <xref:System> contém mais de 100 classes, que vão desde classes que identificam exceções até classes que lidam com os conceitos de tempo de execução, como domínios de aplicativo e o coletor de lixo. O namespace <xref:System> também contém vários namespaces de segundo nível.  
  
 Para obter mais informações sobre namespaces, use o [Navegador de API do .NET](https://docs.microsoft.com/dotnet/api) para procurar a Biblioteca de classes do .NET. A documentação de referência de API fornece informações sobre cada namespace, seus tipos e cada um dos seus membros.  
  
## <a name="see-also"></a>Consulte também

- [Common Type System](../../docs/standard/base-types/common-type-system.md)  
- [Navegador de API do .NET](../../api/index.md)  
- [Visão geral](../../docs/framework/get-started/overview.md)
