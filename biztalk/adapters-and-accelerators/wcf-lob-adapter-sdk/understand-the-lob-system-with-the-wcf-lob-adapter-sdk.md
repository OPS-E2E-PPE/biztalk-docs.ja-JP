---
title: WCF LOB Adapter SDK を使用して LOB システムを理解する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0f97846-5ef2-4530-853a-fba5469156f7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a3a3a44292c3c439c7556bd14e7aa7acadd4fdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362728"
---
# <a name="understand-the-lob-system-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用して LOB システムを理解します。
使用して、アダプターを開発する前に、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ターゲットの基幹業務システムを十分に理解する必要があります。 基幹業務システム、公開する方法、およびセキュリティ、トランザクション、およびその他の機能を提供するサポートのさまざまなレベルで提供される機能を理解していない場合、アダプターはアダプターに必要な機能を提供しません。コンシューマー。 このセクションには、アダプターを効果的にデザインするために理解する必要があります領域がについて説明します。  
  
## <a name="the-path-to-understanding"></a>Understanding へのパス  
 アダプターでは、アダプター仕様やアダプター API による規則に従って、アクセス可能な一貫性のある方法でデータと基幹業務システムから操作を公開します。 どの操作および公開するデータについては、システムの機能とそのデータと操作を公開する方法を理解する必要があります。 具体的には、次のデザインの問題について検討する必要があります。  
  
- **接続のライフ サイクルです。** 方法は接続の開閉しますか。 方法は開いている接続が維持されますか? 接続を再利用するための特別な要件はありますか。 接続の詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IConnection`します。  
  
- **システムによって公開される操作と型メタデータ。** 基幹業務システムでは、操作の検索と参照と、メタデータに簡単にアクセスまたはこの機能を提供するサポート コードを開発する必要がありますか。 たとえば、SQL Server の操作はなどに格納されているオブジェクトの手順です。 列、テーブル、およびその他のオブジェクトの型のメタデータは、簡単に取得できます。 従来の基幹業務システムを使用することは困難があります。  
  
- **どの操作とデータは、システムによって公開されます。** API の公開方法 API のサポート (同期) ブロックと非ブロッキング (非同期) の呼び出しはいますか。 コールバックがサポートされますか。 API またはプロトコル レベルでインターフェイスがでしょうか。  
  
- **セキュリティ、トランザクション、および信頼性の高いメッセージングをサポートします。** API は、これらの機能をサポートする場合、アダプターのコンシューマーに公開する可能性がありますします。 たとえば、SQL Server は、セキュリティと信頼性の高いメッセージング実用的ではありません (ただし、MSMQ、またはその他のキュー システムを使用すること) がサポートするトランザクションがあります。  
  
- **どのような機能と使用状況のシナリオでは重要ですか。** 純粋なテクニカル; についての理解に制限はありません。について説明し、経験豊富なユーザーとビジネス要件をキャプチャします。 一部の操作の一意制約はありますか。 ありますがまだわかりにくい操作に便利ですか。 一部の機能はほとんど使用でしょうか。  
  
  この情報を検出するには、ターゲットの基幹業務システムので、ユーザーとのテクニカル ドキュメントを参照してください。 ドキュメントがスパースまたは不足している場合、オンライン サポート フォーラム、オンラインのニュースグループ、ブログ、または実装の詳細について、インストール ファイルを調べることで、システムの技術的な側面について説明することがあります。 基幹業務の開発者またはコード ファイルにアクセスした場合は、接続のセマンティクスのセキュリティのサポートおよび操作の検索し、呼び出される方法を含む必要な情報を検出することができます。  
  
## <a name="see-also"></a>参照  
 [計画し、WCF LOB Adapter SDK を使用して、アダプターの設計](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [概要、WCF LOB Adapter SDK の使用](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md)   
 [適切なフレームワークを選択します。](https://msdn.microsoft.com/library/bb798089.aspx)