---
title: デジタル証明書を配布する |Microsoft Docs
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
ms.openlocfilehash: 96e11c06288640012dd79b5cd5b0beabce52f5ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378013"
---
# <a name="distributing-digital-certificates"></a>デジタル証明書を配布します。
デジタル署名に使用されるデジタル証明書の発行し、証明機関 (Ca) によってユーザーのワークステーションに配布通常-VeriSign、内部 Ca が組織でホストされているなどの外部か商用エンティティ。 使用されるデジタル証明書の種類 (暗号化アルゴリズムと暗号強度) は、組織で異なる場合があります。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 秘密キーの構成され、デジタル署名や暗号化キー使用法属性の値を持つ証明書形式を使用してフォームのデジタル署名できます。 さらに、証明書の目的は、クライアントの認証として設定する必要があります。  
  
 デジタル証明書の主な目的では、ドキュメントにデジタル署名をドキュメント データの暗号化された一方向ハッシュを作成するのには、その証明書を使用したユーザーを特定します。 データを暗号化されたハッシュは、サインインした後、データに対する変更を検出 (データが変更された場合に生成されませんハッシュは同じ)。 ドメイン ユーザー アカウントとロールに基づくデジタル証明書が発行された (または[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ドメイン グループ)、ユーザー固有のアセットを保護および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証とユーザーのログオン メカニズム。 のみに基づいて、具体的にはに対して発行されたデジタル証明書を使用してドキュメントにデジタル署名することができます、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ドメイン ユーザー アカウント。  
  
 SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] A4SWIFT Message Repair and New Submission にメッセージを送信するたびにすると、デジタル署名 (または副署名) フォーム A4SWIFT によって提供される FormGenerator ユーティリティで生成されたフォーム必要 (を通じて[!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)])。 この要件を回避できません。[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]します。 ただし移動できます[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)](SharePoint Web フォルダーにアクセスするための適切な資格情報があると仮定)、SharePoint Web フォルダーに直接完全と書き込みのメッセージ。 ただし、メッセージに有効なデジタル署名が含まれていない場合 Message Repair and New Submission すぐにメッセージが拒否された、セキュリティ エラーとして。  
  
 メッセージの修復 and New Submission のコンポーネントは、ワークフローの修復、メッセージで使用されるデジタル証明書の公開キーへのアクセスが必要です。 、公開キーを Message Repair and New Submission のアクセスを有効にする各ユーザーは、その他のユーザー ストアに存在する必要がありますの証明書、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Message Repair and New Submission のオーケストレーション サービスをホストするコンピューター。  
  
> [!NOTE]
>  証明書が、メッセージの修復 and New Submission のワークフローで使用され、ユーザー構成メッセージの修復は、VeriSign や e 信頼などの信頼された証明機関によって発行する必要があります。  
  
 内部 Ca を設定する方法の詳細については、MSDN Web サイトで「設定を証明機関」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=48688](http://go.microsoft.com/fwlink/?LinkId=48688)します。