---
title: "FRR NAK ハンドラー サンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009cb0c3dffce5f88c72207866f6778e3deb7b28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-frr-nak-handler-sample-works"></a>FRR NAK ハンドラーのサンプルのしくみ
サンプル FRR NAK カスタム ハンドラーは、FIN 対応調整 (FRR) オーケストレーションとメッセージ修復オーケストレーション間の媒介として機能します。 FRR オーケストレーションでは、SWIFT ネットワークは、メッセージを受信しようとしました。 ときに発生したエラーを識別します。 FRR オーケストレーションの出力は、エラー オブジェクトを 1 つの部分から成るメッセージです。 FRR NAK カスタム ハンドラーは、そのメッセージをメッセージ修復オーケストレーションによって取り出されるメッセージの有効化して発生したエラーを示すエラー部分を含む、2 つの部分のメッセージに変換します。 メッセージ修復オーケストレーションでメッセージを開くと、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム、エラーの確認、同様に、メッセージを修復して再送信することができますができるように[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA を再送信できます。  
  
 次の手順では、FRR NAK カスタム ハンドラーは、SWIFT ネットワークを正常に受信できません。 メッセージを処理するときに発生します。  
  
1.  FRR オーケストレーションには、MTS21_FIN_ACKNAK NAK メッセージに失敗したメッセージが関連付けられますが後、RepairSWIFTRejectedMessage オーケストレーション (カスタム ハンドラー) は、MessageBox から元のメッセージを取得します。 これはため A4SWIFT_FRRFailed でフィルター処理するため = = True および A4SWIFT_SendingServiceType"A4SWIFT_FrrService"を = です。  
  
2.  元のメッセージを相互に関連付けて FRR MTS21_FIN_ACKNAK NAK メッセージ、カスタム ハンドラーは選択されません。 代わりに、エラー コレクション オブジェクトを作成、BRE の検証エラーを示す A4SWIFT_FRRFailedReason プロパティを通知し、元のメッセージに追加の設定。 メッセージ修復オーケストレーションは、この 2 つの部分から成るメッセージを処理できます。  
  
3.  カスタム ハンドラーは、メッセージ修復オーケストレーションによって取り出されるメッセージが発生する次のプロパティを昇格: A4SWIFT_Failed A4SWIFT_SwiftBound を = True、= = = True で、BTS です。操作"A4SWIFT_DASMMarkedAsFailed"を = です。 パーツのプロパティの数を 2 に設定し、適切なエラー プロパティを設定します。  
  
4.  、昇格されたプロパティの結果としてメッセージ修復オーケストレーションがメッセージを取得し、RepairSWIFTRejectedMessage オーケストレーションは終了します。