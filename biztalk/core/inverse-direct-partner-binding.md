---
title: "逆のパートナーの直接バインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c9fe5e51f9f63ea098fa623dafbceeb670e75f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inverse-direct-partner-binding"></a>逆のパートナーの直接バインド
ビジネス プロセス管理ソリューションは、アプリケーションを停止せずに注文処理ステージを変更できるように設計されています。 処理ステージを分離するために (**CableOrder1**、 **CableOrder2**)、プロセス マネージャから (**OrderManager**)、ソリューションのさまざまな手法を使用します。これらのオーケストレーション ポートをバインドします。  
  
 直接バインド、バインドの通常の形式で、 **OrderManager**オーケストレーションは、パートナー オーケストレーションのポートのプロパティの値として処理ステージ オーケストレーションを使用するとします。 次のように直接バインドで、 **OrderManager**オーケストレーションは、厳密な名前 (バージョンを含む) の処理ステージによって異なります。 再配置することがなく処理ステージを変更不可能になります、 **OrderManager**オーケストレーションです。 直接バインドの詳細については、次を参照してください。[ポートのバインド](../core/port-bindings.md)です。 直接バインドは次のようになります。  
  
 ![逆のパートナーの直接バインドの図](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")  
  
 逆のパートナーの直接バインドでは、発信元オーケストレーションではなく受信オーケストレーションがバインドを指定します。 上のポート、 **OrderManager**が単にそれ自体にバインドされています。 上のポートは、 **OrderManager**が指定されて、 **PartnerOrchestrationPort**プロパティです。 ただし、処理ステージ オーケストレーションを適切な使用**OrderManager**ポートの値として、 **PartnerOrchestrationPort**プロパティです。 これは、切り離し、 **OrderManager**処理ステージ オーケストレーションのバージョンを再デプロイしなくても変更することができ、 **OrderManager**です。 直接バインドでは、この分離はできません。 逆のパートナーの直接バインドは次のようになります。  
  
 ![直接バインドの図](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")  
  
> [!NOTE]
>  逆の直接バインドでは、同報リストのような方法でパートナー オーケストレーションとやり取りすることもできます。 **OrderManger** 1 つのポートを使用して、すべてのステージと通信できます。 したがって、オーケストレーションを再設計しないで、ステージを追加または削除できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)