---
title: OrderBroker と OrderManager 間の通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43af6f47a53f28875b77b5089ffe2d343681f140
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357110"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a>OrderBroker と OrderManager 間の通信
注文ブローカと注文マネージャーのオーケストレーション (**OrderBroker**、 **OrderManager**)、メッセージ ボックスされているのではなく、データベースのパートナーの直接バインド経由で通信します。 これにより、ブローカとマネージャは疎結合できるようにする、必要に応じて、別の BizTalk グループおよび地理的に離れた場所に配置されています。 このように、オーケストレーションを分離することにより、管理の構成だけを必要とし、コード変更の必要はありません。  
  
 として現在構成されているソリューションでは、注文ブローカは、特定の順序のマネージャーのメッセージをマークし、メッセージ ボックス データベースに送信します。 さらに、注文マネージャは、対象のメッセージのフィルターをし、それらのメッセージでは、メッセージ ボックス データベースから取得します。 この間接参照-直接バインドするのではなく、メッセージ ボックスを経由して通信-ブローカとマネージャを個別のグループの移動が容易になります。  
  
 別のグループがある、ブローカとマネージャの保守を担当している場合、または地理的に離れた場所に置く必要がある場合は、デザイン簡単に対応します。 行う必要があるすべては、オーケストレーションを別の BizTalk グループに移動します。 オーケストレーションは、別のグループが、再接続は、ポートを作成する必要をのみです。 注文ブローカ グループで、注文マネージャと同じフィルターを持つが、新しいグループにメッセージを転送する送信ポートを作成する必要があります。 注文マネージャ グループでは、メッセージを受信し、メッセージ ボックス データベース内に配置される受信ポートを作成する必要があります。  
  
 エクスポートする、ブローカとマネージャに対して 1 つずつ MSI ファイルを作成することによって、アプリケーションを移動できます。 アプリケーションのエクスポートの詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-business-process-management-solution.md)