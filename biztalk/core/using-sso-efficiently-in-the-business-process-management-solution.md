---
title: ビジネス プロセス管理ソリューションで SSO の効率的な使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, process management solutions
- SSO, configuration values
- caching, configuration values [SSO]
- SSO, caching
- process management solution tutorial, SSO
ms.assetid: 39fbc42d-caa4-4003-a13b-5cde578eb5e1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99575e54b887124bfa4c33fc5257cd057ea818fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288522"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションで SSO の効率的な使用
サービス指向ソリューションと同様に、ビジネス プロセス管理ソリューションは、エンタープライズ シングル サインオン (SSO) を使用して、注文処理ステージの数などの構成値を保存します。 BizTalk がインストールされると存在するため、シークレット ストアを使用します。SSO は、値をすぐに使用できるように構成情報をキャッシュするので、データベース接続文字列やパスワードなどの情報を保護できます。 これらのすべての理由により、SSO がバックエンド アプリケーションの接続管理に使用されていなくても、シークレット ストアは構成情報を保存する適切な場所です。  
  
 待機時間を減らすために、このソリューションでは構成値のローカル キャッシュが使用されます。 キャッシュは 5 分おきに更新されます。  
  
 このトピックでは、このソリューションで使用されるキャッシュ メカニズムについて説明します。 このソリューションは、SSO キャッシュへのアプローチがサービス指向ソリューションと少し異なります。 サービス指向のソリューションの説明では、SSO 値はキャッシュを参照してください[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)です。  
  
## <a name="caching-configuration-values-locally"></a>構成値のローカル キャッシュ  
 ビジネス プロセス管理ソリューションは、単一オブジェクトのプロパティを使用して、SSO 値にアクセスします。  
  
> [!NOTE]
>  単一オブジェクトは 1 つのインスタンスだけを持つオブジェクトなので注意してください。 単一オブジェクトと c# での作成に関する詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)です。  
  
 ソリューションでは、オーケストレーションは最初シングルトン オブジェクトを取得し、オブジェクトのプロパティを使用して、値を参照します。 コードをここでは、 **OrderManager**オーケストレーション。  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 オーケストレーションを呼び出して、**シングルトン**メソッドを**SsoConfigHelper**オブジェクトの 1 つのコピーへのアクセスを取得するオブジェクト。 手の形でオブジェクトが、オーケストレーションが処理ステージの数を取得**TotalStages**です。  
  
 ソリューションに依存して、単一の作成の一般的な方法: コンス トラクターをプライベートにする、オブジェクトがそれ自体のインスタンスを作成して、プライベート変数に割り当てることと、メソッドまたはプロパティでは、その変数の値へのアクセスを提供します。 **SsoConfigHelper**オブジェクト、プロパティを使用して**シングルトン**、それ自体の 1 つのコピーにアクセスできるようにします。  
  
> [!NOTE]
>  **SsoConfigHelper**更新メカニズムを設定して、SSO のキャッシュから初期値を取得するオブジェクトで静的コンス トラクターを使用します。 静的コンストラクタは呼び出せないので、単一オブジェクトのしくみは保持されます。 静的コンス トラクターの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)です。  
  
 直接か間接かに関係なく、オーケストレーションで参照するすべてのオブジェクトは、シリアル化可能にする必要があります。 詳細については、「シリアル化」を参照してください[永続性と、オーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)です。 ただし、 **SsoConfigHelper**オブジェクトが必ずしもシリアル化できる場合は、オーケストレーションで復元オブジェクトの 1 つ、現在のインスタンスを使用すると、エンジンでオーケストレーションを退避します。 シリアル化および BizTalk Server 変数の詳細については、次を参照してください。[オーケストレーション変数の型](../core/orchestration-variable-types.md)です。  
  
> [!NOTE]
>  サービス指向ソリューションのオブジェクトのすべてのパブリック メソッドは、静的です。 このため、このオーケストレーションはインスタンスを変数に割り当てる必要はなく、クラスをシリアル化する必要がありません。  
  
 **SsoConfigHelper**オブジェクトでは、同じメカニズムを使用して取得し、サービス指向ソリューションのように構成値を更新します。 同じパターンのロックも使用されます。 これらのメカニズムの詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)とソース コードの**SsoConfigHelper**です。  
  
 キャッシュでのシングル サインオンは、サービス指向ソリューションの実行と同じように、ビジネス プロセス管理ソリューションを実装する、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**値を格納する名前空間。 ビジネス プロセス管理ソリューションを使用して、 **HybridDictionary**オブジェクトではなく、 **NameValueCollection**オブジェクト。  
  
 サービス指向ソリューションとは異なり、ビジネス プロセス管理ソリューションは、構成データに対応するプロパティを持つオブジェクトを公開します。 これにより、オーケストレーションは、メッセージの種類の違いを処理する必要がなくなります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)