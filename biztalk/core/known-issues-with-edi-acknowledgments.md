---
title: "EDI 受信確認に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02ef54ed8786f8ead12e16fad880040dbcadc8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-acknowledgments"></a>EDI 受信確認に関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI 受信確認に関する既知の問題について説明します。  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a>997 受信確認の AK102 が負の値になる可能性がある  
 X12 997 受信確認の AK102 データ要素 (グループ制御番号) が、負の値になる可能性があります。 AK102 データ要素が負の値である受信確認は、負のグループ制御番号には意味がないにもかかわらず、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって行われる検証に合格します。  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a>メッセージの一部が拒否されても、CONTRL 受信確認で受理の状態がレポートされる可能性がある  
 CONTRL 受信確認 (EDIFACT 技術確認) では、受信した EDIFACT メッセージが重複している場合、またはエンベロープにエラー (文字セットの問題など) がある場合にのみ、[拒否] 状態がレポートされます。 EDIFACT では、X12 による TA1 受信確認の TA104 フィールドでのレポートとは、CONTRL 技術確認で「インターチェンジを受理 (ただしエラーが発生)」状態がレポートされません。 EDIFACT メッセージの一部が受理された場合、CONTRL 技術確認では [受理] がレポートされます。 シナリオによっては、メッセージの一部が拒否されても、CONTRL 受信確認では [受理] の状態がレポートされます。 このようなシナリオでは、UCI5 要素でエラーがレポートされる可能性があります。  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a>グループ ヘッダーまたはトレーラにエラーがある場合、X12 受信確認によって保存済みインターチェンジ (エラーで中断されたインターチェンジ) に対して [受理] が表示される  
 X12 メッセージの受信バッチ処理オプションが [インターチェンジの保存 - エラー発生時にインターチェンジを中断] に設定されており、グループ ヘッダーまたはトレーラのフィールドが無効である場合は、TA1 および 997 受信確認で [受理] の状態がレポートされます。 EDI 状態レポートおよびトランザクション セットの詳細でも [受理] の状態が示されます。 これは、インターチェンジが中断され、イベント ビューアのエラーでインターチェンジの中断が示されている場合でも、発生します。  
  
 TA1 受信確認では [受理] の状態が示されます。これは、GS ヘッダーおよび GE トレーラではなく、ISA ヘッダーおよび IEA トレーラが正しいことを確認する目的があるためです。 ただし、997 受信確認でも [受理] 状態が示されます。  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a>インターチェンジ内のグループの名前が同じである場合に、状態レポートに 2 倍の数の受信確認が表示される  
 同じ名前の複数のグループを持つ EDI インターチェンジを BizTalk Server で処理する場合は、EDI インターチェンジと関連する ACK の状態レポートに、2 倍の数の機能確認が表示されます。 たとえば、インターチェンジ内の 2 つのグループが同じ名前である場合、状態レポートには 2 つでなく 4 つの受信確認が表示されます。  
  
## <a name="see-also"></a>参照  
 [EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [EDI 受信確認を送信します。](../core/sending-an-edi-acknowledgment.md)   
 [受信した確認の処理](../core/processing-a-received-acknowledgment.md)   
 [EDI 受信確認を構成します。](../core/configuring-edi-acknowledgments.md)