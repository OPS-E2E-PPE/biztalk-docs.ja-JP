---
title: 新しいポリシーの展開の作成とメッセージの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43343238-ec45-44ed-a230-9e234bd22d05
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b826b3ee9408caf91fe5adcb2177d709f885a6e1
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25966312"
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a>作成して、新しいメッセージの種類のポリシーを展開します。
作成して、新しいメッセージの種類のポリシーを展開します。  
  
1.  MX メッセージ フォルダー内のメッセージの種類の名前を持つフォルダーを作成します。 たとえば、ここでは、フォルダーの名前になります setr.004.001.02 です。  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  結果として得られるマスターと共にスキーマ ファイル (*.xsd) 配置検証ポリシーは、このフォルダーにこのメッセージの種類のファイルです。  
  
3.  キーワードの名前を持つ MXMessageTypeKeywordList.xml (C:\Program files \microsoft BizTalk Accelerator for swift \sdk\tools) を更新します。 この名前は、メッセージのフォルダー名の最初の 4 つの文字である必要があります。 例を次に示します。  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  特定のマスターを作成する検証ポリシーには、master データベースのコピー//検証ポリシー ファイル、既存のメッセージし、新しいメッセージ フォルダーに配置します。  
  
5.  マスターのメッセージの種類への参照のすべての変更/新しいメッセージの種類を反映するようにポリシーを検証します。  
  
## <a name="message-naming-conventions"></a>メッセージの名前付け規則  
 これらのメッセージ名の規則に従います。  
  
-   **メッセージ名に読み替え**: 新しいメッセージ名が swift.if.ia.setr.004.001.02 ポリシー ファイルが使用されている古いメッセージが pacs.002.001.02 の場合、[すべて置換] と pacs.002.001.02 の出現回数のポリシー ファイル内で swift.if.ia.setr.004.001.02 です。  
  
    > [!NOTE]
    >  メッセージ名はダウンロードされて、スキーマ ファイルの名前であり、メッセージの種類は、メッセージ内のドキュメントの種類の名前です。  
  
-   メッセージ スキーマ自体と同じポリシー ファイルの名前を保持します。 たとえば、swift.if.ia.setr.004.001.02.xsd は、次のポリシー swift.if.ia.setr.004.001.02 _Master_Policy.xml と swift.if.ia.setr.004.001.02 _Validation_Policy.xml があります。  
  
-   **特殊文字**: メッセージ名が、特殊文字を持つかどうかは、ポリシー ファイルを作成すると、若干異なる規則が必要です。 メッセージ名は、たとえば、swift.if.ia$setr.004.001.02 かどうか、は、置き換えられる特殊文字を含むメッセージ名をポリシー ファイルの名前を変更する必要があります"です"。 たとえば、メッセージのスキーマ ファイルの名前が swift.if.ia$setr.004.001.02.xsd の場合は、結果として得られるマスター ポリシー swift.if.ia.setr.004.001.02_Master_Policy.xml はなります。  
  
     また、マスター ポリシー ファイルは、次のタグに新しい名前を反映するように変更する必要があります。  
  
    -   \<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\>  
  
    -   < name="swift.if.ia.setr.004.001.02_Policy_List のルール"