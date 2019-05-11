---
title: CIDX メッセージ規格 |Microsoft Docs
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
ms.openlocfilehash: a39b76ef67374796d9ba569a50e7d5357dac819d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284861"
---
# <a name="cidx-messaging-standards"></a>CIDX メッセージ規格
CIDX (Chemical Industry Data Exchange) は、サポートおよび標準化されたメッセージ交換の Chem eStandards を維持する標準化機構として動作します。 企業、化学工業分野では、業界固有のメッセージング ニーズにこれらの標準を使用します。  
  
 CIDX は、Framework RNIF (RosettaNet Implementation) メッセージング層で XML ドキュメントの交換を有効にするを採用しています。 CIDX は、RNIF 規格のパブリック プロセス層を採用していません。  
  
 Chem eStandards では、システムが交換するメッセージの service content を記述する XML ドキュメント型定義 (Dtd) を定義します。 メッセージでは、service content と一部のヘッダー値に違い構造で、RNIF 1.1 RosettaNet オブジェクトと同じです。 CIDX 規格と RosettaNet メッセージの間の一致がある場合は、RosettaNet の要素名とデータ構造体、CIDX 規格が採用されます。  
  
 CIDX が、メッセージ交換の場合は、電子ドキュメント交換 (EDI) を使用していましたが形式の XML テクノロジに基づいたドキュメントの新しいセット。 Chem eStandards では、EDI メッセージの XML レプリカを提供します。  
  
 Chem eStandards では、各取引に対して個別のメッセージを作成します。 Chem eStandards を使用して、2 つの種類のメッセージ応答: テクニカル応答とトランザクション応答します。 安全で信頼性の高いメッセージング、Chem eStandards は RNIF 1.1 の通知タイプ プロセスのみを使用します。 Chem eStandards では、プロセス PIP (Partner Interface) 0A1 は使用しないでください。  
  
## <a name="cidx-and-rosettanet-differences"></a>CIDX と RosettaNet の違い  
 次の表では、RosettaNet と CIDX の違いの一部を示します。  
  
|RosettaNet の実装|CIDX の実装|  
|-------------------------------|-------------------------|  
|RosettaNet は、Multipurpose Internet Mail Extensions (MIME) の種類として、"Application/x RosettaNet"を使用します。|CIDX は、MIME の種類として"アプリケーション/x-ChemXML"を使用します。|  
|RosettaNet ヘッダー、RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet|CIDX は GlobalAdministeringAuthorityCode = CIDX|  
|RosettaNet では、シングル アクションとダブル アクション メッセージをサポートします。|CIDX では、シングル アクション メッセージのみをサポートします。|  
|RosettaNet PIP 0A1 をサポートしています (エラー通知)。|CIDX は、PIP 0A1 をサポートしていません。|  
|RosettaNet メッセージのトランザクションまたは通知のできる型。|CIDX のすべてのメッセージでは、通知の種類です。|  
|RosettaNet では、PIP 仕様から PIP 構成設定を派生する必要があります。|CIDX では、CIDX Chem eStandards 仕様から PIP 構成設定を派生する必要があります。|  
  
## <a name="see-also"></a>参照  
 [RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)   
 [CIDX サポート](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)