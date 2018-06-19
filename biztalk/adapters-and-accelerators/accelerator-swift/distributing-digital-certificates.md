---
title: デジタル証明書を配布する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- digital signatures
- security, digital signatures
ms.assetid: 3e93a405-3c9b-43f5-bbdf-bec25d43eb45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486a1f45dc6a570bab6518eef215f4133015ead5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209418"
---
# <a name="distributing-digital-certificates"></a>デジタル証明書を配布します。
デジタル署名に使用するデジタル証明書の発行および証明機関 (Ca) によってユーザー ワークステーションに配布されるは通常、VeriSign など内部 Ca が組織でホストされているか外部の商用エンティティです。 使用するデジタル証明書の種類 (暗号化アルゴリズムと暗号強度) は、組織で異なる場合があります。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]秘密キーの構成をデジタル署名や暗号化のキー使用法 属性の値を持つ任意の証明書の形式を使用してフォームをデジタル署名できます。 さらに、クライアント認証と証明書の目的を設定する必要があります。  
  
 デジタル証明書の主な目的は、その証明書を使用して、ドキュメントにデジタル署名し、ドキュメントのデータの暗号化された一方向のハッシュを作成するユーザーを識別します。 データの暗号化ハッシュが署名した後、データに対する変更を検出 (とデータが変更されませんが生成されますハッシュは同じ)。 ドメイン ユーザー アカウントとロールに基づくデジタル証明書が発行された (または[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ドメイン グループ)、ユーザー固有のアセットがで保護されていると[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証とユーザーのログオン メカニズムです。 具体的にを基に発行するデジタル証明書を使用してドキュメントにデジタル署名することができます、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ドメイン ユーザー アカウントです。  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT によって提供される FormGenerator ユーティリティを使用して生成されたフォームを必要とすると、デジタル署名 (または副署名)、フォーム A4SWIFT Message Repair and New Submission にメッセージを送信しようとするたびに (を通じて[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)])。 この要件を回避できません。[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]です。 ただし、移動できます[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)](SharePoint Web フォルダーにアクセスするための適切な資格情報があると仮定した場合)、SharePoint Web フォルダーに直接メッセージを完全と書き込みのメッセージ。 ただし、メッセージに有効なデジタル署名が含まれていない場合 Message Repair and New Submission を直ちに拒否メッセージのセキュリティ エラーとして。  
  
 メッセージの修復および New Submission コンポーネントが、ワークフローを修復、メッセージで使用されるデジタル証明書の公開キーへのアクセスが必要です。 Message Repair and New Submission、公開キーにアクセスを有効にする各ユーザーは、その他のユーザー ストアに、上に存在する必要がありますの証明書を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Message Repair and New Submission オーケストレーション サービスをホストするコンピューター。  
  
> [!NOTE]
>  メッセージの修復 and New Submission のワークフローで使用される証明書とユーザー構成メッセージの修復は、VeriSign や e 信頼などの信頼された証明機関によって発行する必要があります。  
  
 内部 Ca を設定する方法の詳細については、MSDN Web サイトで「設定を証明機関」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=48688](http://go.microsoft.com/fwlink/?LinkId=48688)です。