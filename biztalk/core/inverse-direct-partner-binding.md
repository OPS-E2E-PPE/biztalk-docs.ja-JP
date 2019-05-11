---
title: 逆のパートナーの直接バインド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, partners
- process management solution tutorial, partner binding
ms.assetid: 4cf8717a-2098-46f4-8f58-9d05fb562e2a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ead2c7e7ddf7a56d9a7746f47a7a3fbf1822d7f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330000"
---
# <a name="inverse-direct-partner-binding"></a>逆のパートナーの直接バインド
ビジネス プロセス管理ソリューションは、アプリケーションを停止することがなく処理ステージの順序を変更できるように設計されています。 処理ステージを分離するために (**CableOrder1**、 **CableOrder2**)、プロセス マネージャから (**OrderManager**)、ソリューションのさまざまな手法を使用します。これらのオーケストレーション ポートをバインドします。  
  
 バインドの通常の形式である直接バインド、 **OrderManager**オーケストレーションは、パートナー オーケストレーションのポートのプロパティの値として処理ステージ オーケストレーションを使用するとします。 このような直接バインドで、 **OrderManager**オーケストレーションの処理ステージ (バージョンを含む) 厳密な名前によって異なります。 これにより、再デプロイせず処理ステージを変更不可能な**OrderManager**オーケストレーションします。 直接バインドの詳細については、次を参照してください。[ポートのバインド](../core/port-bindings.md)します。 直接バインドには、この方法を示す可能性があります。  
  
 ![逆のパートナーの直接バインドの図](../core/media/bpm-inverse-direct-binding.gif "BPM_Inverse_Direct_Binding")  
  
 逆のパートナーの直接バインド、受信側のオーケストレーションには、発信元のオーケストレーションではなく、バインディングを指定します。 上のポート、 **OrderManager**自体にバインドされただけです。 上のポートは、 **OrderManager**が指定されて、 **PartnerOrchestrationPort**プロパティ。 ただし、処理ステージ オーケストレーションを適切な使用**OrderManager**ポートの値として、 **PartnerOrchestrationPort**プロパティ。 分離され、 **OrderManager**処理ステージ オーケストレーションのバージョンから再デプロイしなくても変更することを許可し、 **OrderManager**します。 直接バインドでは、このような分離することはできません。 逆の直接パートナーがバインドには、この方法を示す可能性があります。  
  
 ![直接バインドの図](../core/media/bpm-direct-binding.gif "BPM_Direct_Binding")  
  
> [!NOTE]
>  逆の直接バインドも配布リストなどの方法でパートナー オーケストレーションと通信できます。 **OrderManger**すべてのステージとの通信に 1 つのポートを使用することができます。 これにより、追加したり、オーケストレーションを再設計せずステージを削除できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャーのロジック](../core/process-manager-logic.md)