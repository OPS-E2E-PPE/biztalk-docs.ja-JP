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
ms.openlocfilehash: 7e2a4e1efbfb7a86c18fb3643a789312a3707a72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reusing-properties-from-another-agreement"></a>別のアグリーメントのプロパティの再利用
プロパティはアグリーメント間で再利用できます。 これにより、新しいアグリーメントのプロパティのほとんどまたはすべてが、既存のアグリーメントのプロパティと同じ場合には、時間を大幅に節約することができます。 [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] の [!INCLUDE[prague](../includes/prague-md.md)] ユーザー インターフェイスを使用すると、アグリーメントを XML テンプレート ファイルにエクスポートできます。 次に、XML テンプレートをインポートして、アグリーメントの同じプロパティを再利用できます。  
  
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
  
-   [アグリーメントのプロパティを XML ファイルにエクスポートします。](../core/exporting-agreement-properties-to-an-xml-file.md)  
  
-   [アグリーメントのプロパティを XML ファイルからインポートします。](../core/importing-agreement-properties-from-an-xml-file.md)  
  
## <a name="see-also"></a>参照  
 [EDI のプロパティを構成します。](../core/configuring-edi-properties.md)