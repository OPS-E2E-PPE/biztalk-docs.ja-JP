---
title: FRR NAK ハンドラー サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f11bd20-3a0e-4d96-8e0a-32fecc7eed7e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36b64fb92f130defe6bd7d55ac6ccdc3b7391091
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377434"
---
# <a name="how-the-frr-nak-handler-sample-works"></a>FRR NAK ハンドラー サンプルのしくみ
FRR NAK のカスタム ハンドラーのサンプルは、FIN 応答の調整 (FRR) オーケストレーションとメッセージ修復オーケストレーション間の媒介として機能します。 FRR オーケストレーションは、メッセージを受信する SWIFT ネットワークが試行されたときに発生したエラーを識別します。 FRR オーケストレーションの出力は、エラー オブジェクトを 1 つのメッセージです。 FRR NAK のカスタム ハンドラーは、そのメッセージをメッセージ修復オーケストレーションによって取得されるメッセージを有効にすると、発生したエラーを示すエラーの部分で、2 つの部分のメッセージに変換します。 メッセージ修復オーケストレーションでメッセージを開くと、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを使用すると、エラーの確認、メッセージをそれに応じて、修復および再送信するように[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA を再送信できます。  
  
 次の手順は、FRR NAK のカスタム ハンドラーは、SWIFT ネットワークが正常に受信できなかったメッセージを処理するときに発生します。  
  
1.  FRR オーケストレーションが失敗したメッセージを MTS21_FIN_ACKNAK NAK メッセージを相関関係後 RepairSWIFTRejectedMessage オーケストレーション (カスタム ハンドラー) を元のメッセージをメッセージ ボックスから選択します。 これはそのため A4SWIFT_FRRFailed でフィルター処理するため = = True and A4SWIFT_SendingServiceType"A4SWIFT_FrrService"を = です。  
  
2.  元のメッセージに関連する FRR MTS21_FIN_ACKNAK NAK メッセージ、カスタム ハンドラーは選択されません。 代わりに、エラーのコレクション オブジェクトを作成し、A4SWIFT_FRRFailedReason プロパティを通知し、元のメッセージに追加することを示す BRE 検証エラーを設定します。 メッセージ修復オーケストレーションは、この 2 つの部分のメッセージを処理できます。  
  
3.  カスタム ハンドラーは、メッセージがメッセージ修復オーケストレーションによって取得するのには、次のプロパティを昇格します。A4SWIFT_Failed A4SWIFT_SwiftBound を = True、= = = True and BTS します。操作"A4SWIFT_DASMMarkedAsFailed"を = です。 パーツのプロパティの数を 2 に設定し、適切なエラー プロパティを設定します。  
  
4.  昇格されたプロパティの結果としてメッセージ修復オーケストレーションがメッセージを取得し、RepairSWIFTRejectedMessage オーケストレーションが終了します。