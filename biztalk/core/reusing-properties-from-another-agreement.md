---
title: 別のアグリーメント プロパティの再利用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b304af8fbc455a3a18b21774ebc9f1b25e55257
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395598"
---
# <a name="reusing-properties-from-another-agreement"></a>別のアグリーメントのプロパティの再利用
アグリーメントのプロパティを再利用することができます。 これは、かなりのほとんどまたはすべての新しいアグリーメントのプロパティが既存のアグリーメントのものと同じ場合に時間を節約できます。 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server でのユーザー インターフェイスでは、アグリーメントを XML テンプレート ファイルをエクスポートすることができます。 アグリーメントの同じプロパティを再利用する XML テンプレートをインポートできます。  
  
 アグリーメントを XML テンプレートにエクスポートするキャプチャすべてではなく、ほとんどのアグリーメントのプロパティ。 以下のプロパティは*いない*XML テンプレート ファイルにエクスポートします。  
  
- すべてのプロパティ、**全般プロパティ**ページで、**全般**タブ。  
  
- すべてのプロパティ、**連絡先**ページで、**全般**タブ。  
  
- すべてのプロパティ、**追加のプロパティ**ページで、**全般**タブ。  
  
- 識別子に関連する設定から、**識別子**一方向アグリーメント タブのページ。これらの数値は、次のとおりです。  
  
  -   **X12**:ISA5、ISA6、ISA7、ISA8、およびその他のアグリーメント リゾルバーの設定  
  
  -   **Edifact**:UNB 2.1、UNB 2.2、UNB 3.1、UNB 3.2、およびその他のアグリーメント リゾルバーの設定  
  
  -   **AS2 の**:AS2 の AS2 に-から、およびその他のアグリーメント リゾルバーの設定  
  
- 送信ポートの関連付け、**送信ポート**契約の X12、EDIFACT、および AS2 の一方向アグリーメント タブのページします。  
  
  上に示したプロパティ以外は、次のプロパティを XML テンプレート ファイルにエクスポートされます。  
  
- エンコード プロトコル (X12、EDIFACT の場合、または AS2) に関連するすべての設定。  
  
- すべての batch 関連の設定 (バッチ ID) を除く。  
  
> [!NOTE]
>  コピー先のアグリーメントにプロパティをコピーするときに、適用可能なすべてのプロパティが上書きされます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML ファイルへのアグリーメント プロパティのエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [XML ファイルからのアグリーメント プロパティのインポート](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティの構成](../core/configuring-edi-properties.md)