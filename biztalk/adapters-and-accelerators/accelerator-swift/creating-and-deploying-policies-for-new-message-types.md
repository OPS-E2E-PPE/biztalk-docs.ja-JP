---
title: 新しいポリシーの展開の作成とメッセージの種類 |Microsoft Docs
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
ms.openlocfilehash: 570afc1035b9b9430c7f223df4dcec8b82eab756
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378463"
---
# <a name="creating-and-deploying-policies-for-new-message-types"></a>作成して、新しいメッセージの種類のポリシーを展開します。
作成して、新しいメッセージの種類のポリシーを展開します。  
  
1.  MX メッセージ フォルダー内のメッセージの種類の名前のフォルダーを作成します。 たとえば、ここで、フォルダーの名前になります setr.004.001.02 します。  
  
    ```csharp  
    (<xs:complexType name="Document">  
        <xs:sequence>  
            <xs:element name="setr.004.001.02" type="setr.004.001.02"/>  
        </xs:sequence>  
    </xs:complexType>)  
    ```  
  
2.  結果として得られるマスターと共にスキーマ ファイル (*.xsd) の配置/検証ポリシーは、このフォルダーにこのメッセージの種類のファイルします。  
  
3.  キーワードの名前を持つ MXMessageTypeKeywordList.xml (C:\Program files \microsoft BizTalk Accelerator for swift \sdk\tools) を更新します。 この名前は、メッセージ フォルダー名の最初の 4 つの文字である必要があります。 例を次に示します。  
  
    ```csharp  
    (<Keyword name ="setr" />)  
    ```  
  
4.  特定のマスターを作成する検証ポリシーでは、マスター_キーのコピーを実行すると、既存のポリシー ファイルの検証メッセージ、新しいメッセージ フォルダーに配置します。  
  
5.  すべてのマスターのメッセージの種類への参照を変更/新しいメッセージの種類を反映するようにポリシーを検証します。  
  
## <a name="message-naming-conventions"></a>メッセージの名前付け規則  
 メッセージ名のこれらの規則に従います。  
  
-   **メッセージ名に置き換える**:新しいメッセージ名が swift.if.ia.setr.004.001.02 ポリシー ファイルが使用されている古いメッセージが pacs.002.001.02 の場合、すべての pacs.002.001.02 の出現回数に置き換えます swift.if.ia.setr.004.001.02 ポリシー ファイル内で。  
  
    > [!NOTE]
    >  メッセージの名前は、ダウンロードされたスキーマ ファイルの名前と、メッセージの種類は、メッセージ内のドキュメントの種類の名前です。  
  
-   メッセージ スキーマ自体と同じポリシー ファイルの名前を保持します。 たとえば、swift.if.ia.setr.004.001.02.xsd では、次のポリシー swift.if.ia.setr.004.001.02 _Master_Policy.xml と swift.if.ia.setr.004.001.02 _Validation_Policy.xml があります。  
  
-   **特殊文字**:メッセージ名では、それに特殊文字が含まれる場合、ポリシー ファイルの作成、若干異なる規則が必要です。 メッセージ名は、たとえば、swift.if.ia$setr.004.001.02 場合によって置き換えられる特殊文字を含むメッセージ名をポリシー ファイルの名前を変更する必要があります"." たとえば、メッセージのスキーマ ファイルの名前が swift.if.ia$setr.004.001.02.xsd の場合は、結果として得られる、マスタ ポリシー swift.if.ia.setr.004.001.02_Master_Policy.xml はします。  
  
     マスター ポリシー ファイルは、次のタグに新しい名前を反映するように変更する必要があります。  
  
    -   \<ruleset name="swift.if.ia.setr.004.001.02_Master_Policy"\>  
  
    -   < name="swift.if.ia.setr.004.001.02_Policy_List のルール"