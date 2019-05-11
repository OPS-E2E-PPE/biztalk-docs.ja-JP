---
title: EDI 受信確認に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9768bffc83589ae826a9110d994b19b83cdb3fbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380829"
---
# <a name="known-issues-with-edi-acknowledgments"></a>EDI 受信確認に関する既知の問題
このトピックでは、EDI 受信確認に関する既知の問題を説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a>997 受信確認の AK102 が負の値にできます。  
 AK102 データ要素 (グループ制御番号) x12 997 受信確認は、負の値を指定できます。 負の AK102 データ要素を使用して、確認がによって実行される検証を通過[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]負の値のグループ制御番号は意味がないにもかかわらず、します。  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a>CONTRL 受信確認はステータスを報告が受け入れ、メッセージの一部が拒否された場合  
 CONTRL 受信確認 (EDIFACT 技術確認) では、受信した EDIFACT メッセージが重複している場合、またはエンベロープにエラー (文字セットの問題など) がある場合にのみ、[拒否] 状態がレポートされます。 EDIFACT では、X12 による TA1 受信確認の TA104 フィールドでのレポートとは、CONTRL 技術確認で「インターチェンジを受理 (ただしエラーが発生)」状態がレポートされません。 EDIFACT メッセージの一部が受理された場合、CONTRL 技術確認では [受理] がレポートされます。 シナリオによっては、メッセージの一部が拒否されても、CONTRL 受信確認では [受理] の状態がレポートされます。 このようなシナリオでは、UCI5 要素でエラーがレポートされる可能性があります。  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a>X12 では、エラーが受信確認は、保存済みインターチェンジ (エラーでインターチェンジを中断) ときに、グループ ヘッダーやトレーラーの受け入れを表示します。  
 受信バッチ処理オプション、x12 のメッセージは、グループ ヘッダーやトレーラ フィールドと「インターチェンジの保存-エラーでインターチェンジを中断」に設定が有効でない場合は、TA1 および 997 受信確認の両方で 受理の状態が報告されます。 EDI 状態レポートおよびトランザクション セットの詳細は受理 の状態も示します。 これは、インターチェンジが中断され、イベント ビューアーでエラーは、インターチェンジが中断されたことを示す場合でも発生します。  
  
 TA1 受信確認の ISA ヘッダーおよび IEA トレーラー、正確性が GS ヘッダーおよび GE トレーラの正確さないことを確認することが目的のため、受理 のステータスが表示されます。 ただし、997 受信確認は、受理 の状態も表示されます。  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a>インターチェンジ内のグループがある同じ名前、状態レポートに表示されます 2 倍の数の受信確認  
 BizTalk Server では、同じ名前を持つ複数のグループを含む EDI インターチェンジを処理する場合、EDI インターチェンジと関連する ACK の状態レポートで想定どおりに機能確認の 2 倍の数が表示されます。 たとえば、インターチェンジ内の 2 つのグループの同じ名前である場合は、状態レポートは 2 つではなく、4 つの受信確認表示されます。  
  
## <a name="see-also"></a>参照  
 [EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [EDI 受信確認を送信します。](../core/sending-an-edi-acknowledgment.md)   
 [受信確認の処理](../core/processing-a-received-acknowledgment.md)   
 [EDI 受信確認の構成](../core/configuring-edi-acknowledgments.md)