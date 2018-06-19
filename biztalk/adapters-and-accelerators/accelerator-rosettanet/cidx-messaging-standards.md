---
title: CIDX メッセージ規格 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d37cd02f92a8a13857071d0b3d84ab40c480787
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207258"
---
# <a name="cidx-messaging-standards"></a>CIDX メッセージ規格
CIDX (Chemical Industry Data Exchange) は、標準化されたメッセージ交換の Chem eStandards をサポートおよび維持する標準化機構です。 化学工業分野の企業では、この規格を利用して、業界特有のメッセージングのニーズに対応します。  
  
 CIDX では、XML ドキュメントの交換を可能にするために、メッセージ層に RNIF (RosettaNet Implementation Framework) を採用しています。 CIDX では、RNIF 規格のパブリック プロセス層は採用していません。  
  
 Chem eStandards は、システムが交換するメッセージの Service Content を記述する XML 文書型定義 (DTD) を定義します。 メッセージの構造は RNIF 1.1 RosettaNet オブジェクトと同じですが、Service Content と一部のヘッダー値が異なります。 CIDX 規格と RosettaNet メッセージに一致がある場合、CIDX 規格では RosettaNet の要素名とデータ構造を採用します。  
  
 CIDX では、これまでメッセージ交換に EDI (Electronic Document Interchange) を使用していましたが、XML テクノロジに基づいた新しいドキュメント セットを作成しました。 Chem eStandards により、EDI メッセージの XML レプリカが作成されます。  
  
 Chem eStandards により、各取り引きに対して個別のメッセージが作成されます。 Chem eStandards では、テクニカル応答とトランザクション応答の 2 種類のメッセージ応答を使用します。 安全で信頼できるメッセージ処理のために、Chem eStandards では RNIF 1.1 の通知タイプ プロセスのみを使用します。 PIP (Partner Interface Process) 0A1 は使用しません。  
  
## <a name="cidx-and-rosettanet-differences"></a>CIDX と RosettaNet の違い  
 次の表に、RosettaNet と CIDX の違いの一部を示します。  
  
|RosettaNet の実装|CIDX の実装|  
|-------------------------------|-------------------------|  
|RosettaNet は、MIME (Multipurpose Internet Mail Extensions) の種類として "Application/x-RosettaNet" を使用します。|CIDX は、MIME の種類として "Application/x-ChemXML" を使用します。|  
|RosettaNet は、RosettaNet ヘッダーとして GlobalAdministeringAuthorityCode = RosettaNet を使用します。|CIDX は、GlobalAdministeringAuthorityCode = CIDX を使用します。|  
|RosettaNet は、シングル アクションとダブル アクションのメッセージをサポートします。|CIDX は、シングル アクションのメッセージのみをサポートします。|  
|RosettaNet は、PIP 0A1 (エラー通知) をサポートします。|CIDX は、PIP 0A1 をサポートしません。|  
|RosettaNet メッセージの種類は、Transaction または Notification です。|CIDX メッセージの種類はすべて Notification です。|  
|RosettaNet では、PIP 仕様に基づいて PIP 構成設定を作成する必要があります。|CIDX では、CIDX Chem eStandards 仕様に基づいて PIP 構成設定を作成する必要があります。|  
  
## <a name="see-also"></a>参照  
 [RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)   
 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)