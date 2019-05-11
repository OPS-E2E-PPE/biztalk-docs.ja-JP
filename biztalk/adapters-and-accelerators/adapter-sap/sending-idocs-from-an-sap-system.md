---
title: BizTalk での mySAP アダプターを使用する SAP システムから Idoc を送信する |Microsoft Docs
description: ''
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b194afbc0fff102c9c3a7017f24610234a88ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372866"
---
# <a name="sending-idocs-from-an-sap-system"></a>SAP システムから Idoc を送信します。
外部のアプリケーションに、SAP システムから IDOC を送信する SAP システムで完了する高度なタスク。 これらのタスクを実行するため、SAP 管理者にお問い合わせくださいまたは SAP のガイダンスを参照してください。  
  
## <a name="send-an-idoc-from-sap"></a>SAP からの IDOC を送信します。  
  
1.  SAP GUI を起動します。  
  
2.  BD54 トランザクションを使用して論理システムを作成します。  
  
3.  SM59 トランザクションを使用して TCP/IP 接続では、RFC 転送先を作成します。  
  
4.  WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。  
  
5.  IDOC の種類と必要なメッセージの種類と WE20 トランザクションを使用してパートナー プロファイルを作成し、最後の手順で作成したポートにアタッチします。  
  
6.  メッセージの種類を販売トランザクションを使用して、ポートに接続することで、分散型モデルを維持します。  
  
7.  SAP の IDOC を生成します。 たとえば、BD10 トランザクションを使用して、MATMAS IDOC をトリガーします。 特定の Idoc をトリガーするには、他のトランザクションについては、SAP 管理者にお問い合わせください。  

## <a name="view-transaction-ids-in-sap"></a>SAP でトランザクション Id の表示
ときに、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC を呼び出すか、IDOC を SAP システムのレジスタの SAP システムにトランザクション ID (TID) の応答で送信します。 一部のシナリオからの呼び出しに対する応答で SAP システムに登録されている TID を把握する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 たとえば、問題をトラブルシューティングする SAP システムでの作業 (LUW) の論理単位を識別します。  
  
 SAP システムで、Tid を表示するには、SM58 トランザクションを使用する必要があります。 SAP 管理者に問い合わせるか、このトランザクションの詳細については、SAP のガイダンスを参照してください。 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a>送信され、SAP から受信した Idoc に関する詳細を表示
使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]IDOC を SAP システムに送信または SAP システムから IDOC を受信できます。 状態と送信または受信された IDOC のデータ ビューでの SAP システムを追跡するには、WE02 トランザクションを使用することができます。 SAP の管理者に問い合わせるか、このトランザクションの詳細については、SAP のガイダンスを参照してください。  

  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)