---
title: "Order Handler オブジェクトを使用して、バックエンド システムと通信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7621c4e5737def0e9fc0682de709ae57f98790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a>Order Handler オブジェクトを使用して、バックエンド システムと通信するには
最終的な注文を受信する既存のバックエンド システムである Cable Provisioning System とビジネス プロセス管理ソリューションが通信する方法は多数存在します。 このソリューションでは、Microsoft [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] で提供されている .NET リモート処理機能を使用して Provisioning System と通信します。  
  
 このソリューションでは、インターフェイスを使用してバックエンド システムに対するアクセス オブジェクトを定義する一般的な方法を使用します。 独立したアセンブリにインターフェイスを配置することにより、クライアント アセンブリは、コンパイルされたアセンブリにアクセスする必要なく、リモート オブジェクトにアクセスできます。  
  
 **IOrderHandler**インターフェイスが、バックエンド注文システムと通信するメソッドを定義します。 このインターフェイスには、注文の分析、アクティブ化、取り消し、および完了を行うためのメソッドが含まれています。 サービスの種類、注文が取り消されたときに必要なメソッドを識別するためのメソッドも用意されています。  
  
 **CableOrder1**、 **CableOrder2**、サテライト オーケストレーションを使用して、 **OrderHandlerWrapper**を実装するオブジェクト**IOrderHandler**. **OrderHandlerWrapper**オブジェクト、さらのリモート インスタンスを起動、 **OrderHandler**オブジェクトによって提供される、 **CableProvisioningSystemServer**実行可能ファイルです。 ラッパー オブジェクトを使用することにより、バックエンドの注文システムと通信するために .NET リモート処理を使用するビジネス要件が満たされ、例外処理コンポーネントの再試行機能の使用が有効になります。  
  
 いずれかのオーケストレーションで参照されているすべてのオブジェクトをシリアル化できる必要がありますので、 **OrderHandlerWrapper**もシリアル化することができます。 使用して、 **OrderHandlerWrapper**オーケストレーションからシリアル化コードを分離します。  
  
 Se がわかる場合は、コードを見るを**OrderHandlerWrapper**オブジェクトが明示的に実装する、 **ISerializable**インターフェイスです。 このオブジェクトは既定以外のコンストラクタを使用するので、自身のシリアル化を処理する必要があるのです。  
  
 バックエンド システムと通信するために .NET リモート処理を使用することは、メッセージングを使用するよりも効率的で、 単純なメッセージング ソリューションを使用した場合よりも、オーケストレーションがバックエンド システムに緊密にバインドされます。 また、.NET リモート処理を使用することにより、BizTalk Server の組み込みの機能が再試行要求に対して使用される状況を回避できます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)