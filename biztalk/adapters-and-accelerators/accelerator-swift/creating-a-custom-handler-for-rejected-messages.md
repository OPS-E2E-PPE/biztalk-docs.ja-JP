---
title: "メッセージを拒否するカスタム ハンドラーを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa02ad0fcb0236ec879e43b44a891fcdf591beb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a>拒否されたメッセージのカスタム ハンドラーの作成
検証または承認の段階でメッセージを拒否した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)](ここでは常に修復する場合でも、作成は、ワークフローの最初のステージ) をワークフローに対して定義されている最初のステージにメッセージが返されます。 ただし、ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションは、メッセージ公開メッセージ ボックスに MrsrRepair オーケストレーションにメッセージが拒否されたことを示す昇格させたプロパティを持つ。 これらのメッセージを処理するには、これらの昇格させたプロパティをサブスクライブし、必要に応じてメッセージを処理するカスタム ハンドラー (オーケストレーション) を作成できます。  
  
 メッセージは、MrsrRepair オーケストレーションで複数の理由により失敗します。 オーケストレーションは、次の表に、プロパティを昇格し、値、またはテーブルの右側の列に示すように、値のいずれか、これらのプロパティを割り当てます。  
  
|プロパティ|値|  
|--------------|------------|  
|BTS です。操作|A4SWIFT_MRSRFailed|  
|A4SWIFT_MRSRFailedReason|Timeout<br /><br /> 拒否された (場合は、メッセージは、最初のステージから拒否されました)<br /><br /> CantRepairInInfoPath|  
|A4SWIFT_MRSRLastStage|\<最後のステージ (ロール) が失敗する前にあったメッセージの名前\>|  
|A4SWIFT_MRSRDepartment|\<部門の名前\>|