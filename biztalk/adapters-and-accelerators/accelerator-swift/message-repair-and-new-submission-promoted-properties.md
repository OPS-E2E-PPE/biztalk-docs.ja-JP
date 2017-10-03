---
title: "Message Repair and New Submission の昇格させたプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, Message Repair and New Submission
- Message Repair and New Submission, promoted properties
ms.assetid: e980c905-d07f-4fc2-89ca-05e597410733
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76e4f57e9f5179ceea073ef281131a8cd3573703
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-repair-and-new-submission-promoted-properties"></a>Message Repair and New Submission の昇格させたプロパティ
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の調整には、次の昇格させたプロパティが含まれています。  
  
|昇格の名前|Description|データ型|値の範囲|使用例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**BTS です。操作**|状態を示す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を処理します。 次のいずれかになります。<br /><br /> **A4SWIFT_MrsrCompleted**メッセージ修復し、新しい送信プロセスが成功したことを示します。<br /><br /> **A4SWIFT_MrsrFailed**メッセージ修復し、新しい送信プロセスが失敗したことを示します。<br /><br /> **A4SWIFT_MrsrUnparsedFailed**未解析のメッセージの修復が失敗したことを示します。<br /><br /> **A4SWIFT_MrsrUnparsedComplete**未解析のメッセージの修復が成功したことを示します。<br /><br /> **A4SWIFT_DasmMarkedAsFailed**メッセージに、受信パイプラインの逆アセンブラー ステージで処理が失敗したことを示します。|文字列|-A4SWIFT_MrsrCompleted<br />-A4SWIFT_MrsrFailed<br />-A4SWIFT_MrsrUnparsedFailed<br />-A4SWIFT_MrsrUnparsedCompleted<br />-A4SWIFT_DasmMarkedAsFailed|MrsrRepair オーケストレーションは、修復後に修復された解析されていないメッセージを受信したときに、設定、 **BTS です。操作**プロパティを"A4SWIFT_MRSRCompleted"および**A4SWIFT_Failed**プロパティを False にし、メッセージ ボックスにメッセージをルーティングします。 これらのプロパティでは、こと解析されていないメッセージを入力していないメッセージの修復プロセス再度を確認してください。|  
|**Microsoft.Solutions.A4SWIFT です。Property.A4SWIFT_Failed**|示すかどうか[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]成功と失敗のメッセージを処理します。|ブール値|True、False|検証に失敗したメッセージ ボックス データベースからのメッセージのみにサブスクライブする MrsrRepair オーケストレーションで使用します。|  
|**Microsoft.Solutions.A4SWIFT です。Property.A4SWIFT_SwiftBound**|SWIFT ネットワークには、メッセージがバインドされているかどうかを示します。|ブール値|True、False|SWIFT ネットワークにバインドされているメッセージ ボックス データベースからのメッセージのみにサブスクライブする MrsrRepair オーケストレーションで使用します。|  
|**Microsoft.Solutions.A4SWIFT です。MRSRProperty.A4SWIFT_MRSRIsNewSubmission**|処理対象のメッセージが、新しい送信であるかどうかを示します。|ブール値|True、False|MrsrRepair オーケストレーションで使用すると、ワークフローの作成の段階でメッセージが作成されたことを指定します。|  
|**Microsoft.Solutions.A4SWIFT です。MRSRProperty.A4SWIFT_MRSRLastStage**|成功した修復ワークフローの最後のステージを示します。|文字列|-|部門のワークフローに対して定義されているステージのいずれか。 作成することができます、修復、キー更新を確認、または承認ステージです。|  
|**Microsoft.Solutions.A4SWIFT です。MRSRProperty.A4SWIFT_ MRSRDepartment**|メッセージの修復と MrsrDepartmentPolicy BRE ポリシーで指定された、新しい送信で使用されている部門を示します。|文字列|-|設定、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールです。|  
|**Microsoft.Solutions.A4SWIFT です。MRSRProperty.A4SWIFT_ MRSRFailedReason**|新しい送信プロセスとメッセージの修復が失敗した理由を示します。 次のいずれかになります。<br /><br /> 拒否されたユーザーが内からメッセージを拒否されたことを示す、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。<br /><br /> InvalidDigitalSignature では、ユーザーの証明書が無効であることを示します。<br /><br /> タイムアウトは、MRSROrchestration タイムアウト値に達していることを示します。<br /><br /> InvalidWorkFlow では、部門に対して定義されているワークフローが無効であることを示します。<br /><br /> CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]に受信 XML メッセージを開けなかったことを示す[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]です。<br /><br /> 一般的な例外|文字列|-拒否<br />-InvalidDigitalSignature<br />タイムアウト<br />-InvalidWorkFlow<br />-一般例外<br />-CantRepairIn[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]|プロセスが失敗した後は、Message Repair and New Submission のオーケストレーションによって設定されます。|  
  
## <a name="see-also"></a>参照  
 [A4SWIFT_ * 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [昇格させたプロパティの FIN 対応調整](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation-promoted-properties.md)