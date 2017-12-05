---
title: "別のアグリーメント プロパティの再利用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8e1cc60-d581-43ca-aa70-1e0d6238497a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7db2118f372014a3e8f108c1ff2273bc5aad976
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="reusing-properties-from-another-agreement"></a>別のアグリーメントのプロパティの再利用
プロパティはアグリーメント間で再利用できます。 これにより、新しいアグリーメントのプロパティのほとんどまたはすべてが、既存のアグリーメントのプロパティと同じ場合には、時間を大幅に節約することができます。 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] BizTalk Server でのユーザー インターフェイスでは、アグリーメントを XML テンプレート ファイルをエクスポートすることができます。 次に、XML テンプレートをインポートして、アグリーメントの同じプロパティを再利用できます。  
  
 アグリーメントを XML テンプレートにエクスポートすると、すべてではないものの、アグリーメントのほとんどのプロパティが取り込まれます。 以下のプロパティは*いない*XML テンプレート ファイルにエクスポートします。  
  
-   すべてのプロパティ、**全般プロパティ** ページで、**全般**タブです。  
  
-   すべてのプロパティを**連絡先** ページで、**全般** タブ。  
  
-   すべてのプロパティを**追加のプロパティ** ページで、**全般** タブ。  
  
-   識別子関連の設定から、**識別子**一方向アグリーメント タブのページでします。これらの設定は、次のとおりです。  
  
    -   **X12**: ISA5、ISA6、ISA7、ISA8、およびその他のアグリーメント リゾルバーの設定  
  
    -   **Edifact**: UNB 2.1、UNB 2.2、UNB 3.1、UNB 3.2、およびその他のアグリーメント リゾルバーの設定  
  
    -   **AS2 の**: AS2-には、AS2-、およびその他のアグリーメント リゾルバーの設定  
  
-   送信ポートの関連付け、**送信ポート**契約の X12、EDIFACT、および AS2 の一方向アグリーメント タブのページです。  
  
 上記に示したプロパティ以外の、次のプロパティは XML テンプレート ファイルにエクスポートされます。  
  
-   エンコード プロトコル関連のすべての設定 (X12、EDIFACT、または AS2)。  
  
-   バッチ関連のすべての設定 (バッチ ID を除く)。  
  
> [!NOTE]
>  適用できるすべてのプロパティは、コピー先のアグリーメントにプロパティをコピーしたときに上書きされます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML ファイルへのアグリーメント プロパティのエクスポート](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [XML ファイルからのアグリーメント プロパティのインポート](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティの構成](../core/configuring-edi-properties.md)