---
title: メッセージは拒否のカスタム ハンドラーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom handlers
- Message Repair and New Submission, rejected messages
- Message Repair and New Submission, custom handlers
ms.assetid: 28d74504-6c62-427a-b75d-456fbe43ec3a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fb2ebe02d4f64923239bb67aa3667ac4f3ff0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378496"
---
# <a name="creating-a-custom-handler-for-rejected-messages"></a>拒否されたメッセージのカスタム ハンドラーを作成します。
認証または承認ステージでは、メッセージを拒否した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)](ここでは常に修復する場合でも、作成は、ワークフローの最初のステージ) をワークフローに対して定義されている最初のステージにメッセージが返されます。 ただし、ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションは、メッセージ公開メッセージ ボックスに MrsrRepair オーケストレーションにメッセージが拒否されたことを示す昇格させたプロパティ。 これらのメッセージを処理するには、これらの昇格させたプロパティをサブスクライブし、必要に応じてメッセージを処理するカスタム ハンドラー (オーケストレーション) を作成できます。  
  
 メッセージは、複数の理由から MrsrRepair オーケストレーションで失敗することができます。 オーケストレーションは次の表にプロパティを昇格し、値、またはテーブルの右側の列に表示される、値の 1 つは、これらのプロパティを割り当てます。  
  
|プロパティ|値|  
|--------------|------------|  
|BTS します。操作|A4SWIFT_MRSRFailed|  
|A4SWIFT_MRSRFailedReason|Timeout<br /><br /> 拒否された (場合は、最初の段階から、メッセージは拒否されました)<br /><br /> CantRepairInInfoPath|  
|A4SWIFT_MRSRLastStage|\<メッセージが失敗するまでが含まれる最後のステージ (ロール) の名前\>|  
|A4SWIFT_MRSRDepartment|\<部門の名前\>|