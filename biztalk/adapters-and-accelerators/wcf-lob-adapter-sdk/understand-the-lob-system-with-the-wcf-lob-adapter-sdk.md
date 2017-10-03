---
title: "WCF LOB Adapter SDK を使用して LOB システムを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0f97846-5ef2-4530-853a-fba5469156f7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d777022312c8511608519d155626c948da3efdb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して LOB システムを理解します。
使用して、アダプターを開発する前に、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]対象の基幹業務システムを十分に理解する必要があります。 基幹業務システム、公開、およびセキュリティ、トランザクション、およびその他の機能を提供するサポートのさまざまなレベルで提供される機能を理解していない場合、アダプターが提供されない機能がアダプタで必要なコンシューマー。 このセクションでは、効果的に使用してアダプターをデザインするために理解する必要があります領域について説明します。  
  
## <a name="the-path-to-understanding"></a>Understanding へのパス  
 アダプターの目的は、アダプターの仕様やアダプター API による規則に従って、一貫性のあるアクセス可能な方法でデータと基幹業務システムからの操作を公開します。 調べるにはどの操作および公開するデータ、システムの動作やをそのデータや操作を公開する方法を理解する必要があります。 具体的には、次のデザインに関する問題を検討する必要があります。  
  
-   **接続のライフ サイクルです。** 方法は、接続の開閉しますか。 どの開いている接続が維持されますか。 接続を再利用するための特別な要件はありますか。 接続の詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IConnection`です。  
  
-   **操作と型のメタデータをシステムによって公開されています。** 基幹業務システム操作の検索および参照とサポートのメタデータに簡単にアクセスまたはこの機能を提供するサポート コードを開発する必要がありますか。 たとえば、SQL Server 操作など、格納されているオブジェクトは手順はします。 列、テーブル、およびその他のオブジェクトの型のメタデータは、簡単に取得できます。 従来の基幹業務システムを使用することは困難があります。  
  
-   **どの操作とデータは、システムによって公開されます。** API の公開方法 API サポート (同期) をブロックおよび非ブロッキング (非同期) 呼び出しをか。 コールバックがサポートされますか。 API またはプロトコル レベルで接続されますか。  
  
-   **セキュリティ、トランザクション、および信頼できるメッセージングをサポートします。** API は、これらの機能をサポートする可能性がありますする場合、アダプターのコンシューマーには公開します。 たとえば、SQL Server は、セキュリティやトランザクションのサポートが、信頼できるメッセージングでは使用できません (ただし、MSMQ、またはその他のキュー システムを使用すること) にします。  
  
-   **どのような機能と使用状況のシナリオが重要であります。** 純粋なテクニカル; についての理解を制限しません。について説明し、経験豊富なユーザー、ビジネス要件をキャプチャします。 一部の操作に一意制約があるか。 あるがまだであいまいな操作には便利ですか。 一部の機能はほとんど使用しますか。  
  
 この情報を探索するには、対象の基幹業務システムでユーザーおよび技術ドキュメントを参照してください。 ドキュメントがスパース ファイルまたは不足している場合もオンライン サポート フォーラム、オンラインのニュースグループ、ブログなどを調べることで、または実装の詳細について、インストール ファイルを確認するには、システムの技術的な側面について学習することがあります。 基幹業務開発者またはコード ファイルにアクセスした場合は、接続セマンティクスのサポート、セキュリティ、および操作の検索し、呼び出される方法を含む必要な情報を探索することができます。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [概要、WCF LOB Adapter SDK と](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [適切なフレームワークを選択します。](https://msdn.microsoft.com/library/bb798089.aspx)