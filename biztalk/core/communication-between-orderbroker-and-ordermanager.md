---
title: "OrderBroker と OrderManager 間の通信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="communication-between-orderbroker-and-ordermanager"></a>OrderBroker と OrderManager 間の通信
注文ブローカと注文マネージャーのオーケストレーション (**OrderBroker**、 **OrderManager**)、メッセージ ボックス データベースはなくのパートナーの直接バインド経由で通信します。 これにより、ブローカとマネージャは疎結合して、必要に応じて個別の BizTalk グループおよび地理的に分散した場所に存在できます。 このようにオーケストレーションを分割するときに必要なのは、管理の構成だけです。コードの変更は必要ありません。  
  
 現在構成されているソリューションでは、注文ブローカは、特定の注文マネージャのメッセージをマークし、それらのメッセージをメッセージ ボックス データベースに送信します。 次に、注文マネージャは、対象のメッセージのフィルタ処理を行い、メッセージ ボックス データベースからそれらのメッセージを取得します。 間接的なこの方法 (直接バインドではなくメッセージ ボックス データベースを通じた通信) により、ブローカとマネージャを個別のグループに簡単に移動できます。  
  
 ブローカとマネージャを保存するさまざまなグループが存在する場合または地理的に分散した場所にブローカとマネージャを格納する場合も、この設計によって、簡単に対応できます。 必要な作業は、オーケストレーションを異なる BizTalk グループに移動するだけです。 オーケストレーションを個別のグループに格納した後にポートを作成するには、オーケストレーションの再接続だけが必要です。 注文ブローカ グループで、注文マネージャと同じフィルタを使用している (メッセージを新しいグループに転送する) 送信ポートを作成する必要があります。 注文マネージャ グループで、メッセージを受信してメッセージ ボックス データベースにメッセージを配置する受信ポートを作成する必要があります。  
  
 アプリケーションをエクスポートして MSI ファイル (ブローカとマネージャに 1 つずつ) を作成することにより、アプリケーションを移動できます。 アプリケーションのエクスポートの詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)