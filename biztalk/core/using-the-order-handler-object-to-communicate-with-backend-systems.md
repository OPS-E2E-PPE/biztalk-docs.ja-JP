---
title: Order Handler オブジェクトを使用してバックエンド システムと通信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOrderHandler interface
- process management solution tutorial, IOrderHandler interface
ms.assetid: b9fe4120-bf2a-4d15-a34b-6b98f026b984
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 919013bbae989d588033437be54ce705179a44f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303005"
---
# <a name="using-the-order-handler-object-to-communicate-with-backend-systems"></a>Order Handler オブジェクトを使用してバックエンド システムと通信
ビジネス プロセス管理ソリューションがある cable provisioning system 最終的な注文を受信する、従来のバックエンド注文システムと通信でした多くの方法はあります。 ソリューションについては、Microsoft .NET リモート処理機能を使用する[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]provisioning system と通信します。  
  
 ソリューションでは、インターフェイスを使用して、バックエンド システムに対するアクセス オブジェクトを定義する一般的な手法を使用します。 アセンブリは、別のアセンブリでは、クライアントで、インターフェイスを配置することで、コンパイルされたアセンブリにアクセスすることがなくリモート オブジェクトへのアクセスができます。  
  
 **IOrderHandler**インターフェイスは、バックエンド注文システムと通信するメソッドを定義します。 インターフェイスには、分析、アクティブ化、取り消し中、および注文を完了するためのメソッドが含まれています。 サービスの種類、注文がキャンセルされた場合に必要なメソッドを識別するためのメソッドも提供します。  
  
 **CableOrder1**、 **CableOrder2**、サテライト オーケストレーションを使用して、 **OrderHandlerWrapper**を実装するオブジェクト**IOrderHandler**. **OrderHandlerWrapper**オブジェクト、さらのリモート インスタンスを呼び出す、 **OrderHandler**オブジェクトによって提供される、 **CableProvisioningSystemServer**実行可能ファイルです。 使用した .NET リモート処理通信中に、バックエンド注文システムを同時に、例外処理コンポーネントの再試行機能の使用を有効にするのビジネス要件を満たしている、ラッパー オブジェクトを使用します。  
  
 1 つ、オーケストレーションで参照されているすべてのオブジェクトをシリアル化できる必要がありますので、 **OrderHandlerWrapper**もシリアル化することができます。 使用して、 **OrderHandlerWrapper**はシリアル化コードをオーケストレーションから分離します。  
  
 場合は、コードを見ることがわかりますが、 **OrderHandlerWrapper**オブジェクトを明示的に実装して、 **ISerializable**インターフェイス。 オブジェクトは、既定以外のコンス トラクターを使用しているために、独自のシリアル化を処理する必要があります。  
  
 .NET リモート処理を使用して、バックエンド システムとの通信には、メッセージングを使用するよりも効率的です。 一方で、オーケストレーションのバインドより緊密にバックエンド システムによりも、純粋なメッセージング ソリューションの可能性があります。 .NET リモート処理を使用しても防止ソリューション再試行要求に対して組み込みの BizTalk Server の機能を活用します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャーのロジック](../core/process-manager-logic.md)