---
title: 複数の MSMQ アダプターを使用して場所の受信を管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b46ab60e3e5073c7c487ffb530dbc0407b0444f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384707"
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a>複数の MSMQ アダプターを使用して場所の受信を管理する方法
パフォーマンスを向上させるのには、MSMQ アダプターがマルチ スレッドです。 多くの受信場所があれば、ある可能性がありますいないのに十分なスレッドすべての受信場所の使用可能です。 これは、いくつかの受信場所でメッセージを取得できないようにします。 この問題を解決するために 3 つの方法はあります。  
  
-   お使いのコンピューターに BizTalk ホストを追加し、ホスト間で受信場所を分割します。 受信場所の使用可能な多くのスレッドは、ホストを追加します。  
  
-   設定、**シリアル処理**プロパティを`True`各受信場所。 プロパティを設定する`True`受信場所の 1 つのスレッドのそれぞれに割り当てられます。 これにより、プールで使用可能な多くのスレッドが残ります。 ただし、パフォーマンスの低下がありますも。  
  
-   MSMQ アダプターの受信ハンドラーのホストに利用できるスレッドの数を増やすにレジストリを変更します。 詳細については、次を参照してください。、**ホスト用 CLR Hosting スレッド値を変更**の[構成パラメーターを アダプターのパフォーマンスの影響を与える](../core/configuration-parameters-that-affect-adapter-performance.md)します。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)