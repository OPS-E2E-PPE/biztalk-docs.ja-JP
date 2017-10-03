---
title: "BizTalk で、mySAP アダプターを使用する SAP システムから Idoc を送信する |Microsoft ドキュメント"
description: 
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aea8a5e9-d775-4d52-a434-c2908b53cd2d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63f7d1ccdaa8cb6a4ee12ad1cc4263c487a164c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sending-idocs-from-an-sap-system"></a>SAP システムから Idoc を送信します。
SAP システムから IDOC を外部アプリケーションに送信する SAP システムで完了する高度なタスクです。 これらのタスクを実行するため、SAP 管理者に問い合わせてまたは SAP ガイダンスを参照してください。  
  
## <a name="send-an-idoc-from-sap"></a>SAP からの IDOC を送信します。  
  
1.  SAP の GUI を起動します。  
  
2.  BD54 トランザクションを使用して論理システムを作成します。  
  
3.  SM59 トランザクションを使用して TCP/IP 接続で、RFC 変換先を作成します。  
  
4.  WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。  
  
5.  IDOC タイプと必須のメッセージ型と WE20 トランザクションを使用して、パートナー プロファイルを作成し、最後の手順で作成したポートにアタッチします。  
  
6.  メッセージの種類を販売トランザクションを使用してポートに接続することで、分散モデルを維持します。  
  
7.  SAP 内で IDOC を生成します。 たとえば、MATMAS IDOC をトリガーするのに BD10 トランザクションを使用します。 特定の Idoc をトリガーするには、他のトランザクションについては、SAP 管理者にお問い合わせください。  

## <a name="view-transaction-ids-in-sap"></a>SAP でトランザクション Id の表示
ときに、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC を呼び出すか、IDOC が SAP システムのレジスタ、SAP システムにトランザクション ID (TID) の応答として送信します。 一部のシナリオでからの呼び出しに応答内の SAP システムに登録されている TID を知っている必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 たとえば、問題のトラブルシューティングを SAP システム上の作業 (LUW) の論理ユニットを識別することができます。  
  
 SAP システムで、Tid を表示するには、SM58 トランザクションを使用する必要があります。 SAP 管理者に問い合わせるか、このトランザクションの詳細については、SAP のガイダンスを参照してください。 

## <a name="view-details-about-idocs-sent-and-received-from-sap"></a>送信され、SAP から受信した Idoc に関する詳細を表示
使用して、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]IDOC を SAP システムに送信または SAP システムから IDOC を受信できます。 状態とを IDOC のデータが送信または受信されたビューを SAP システムを追跡、WE02 トランザクションを使用することができます。 SAP 管理者に問い合わせて、またはこのトランザクションの詳細については、SAP のガイダンスを参照してください。  

  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)