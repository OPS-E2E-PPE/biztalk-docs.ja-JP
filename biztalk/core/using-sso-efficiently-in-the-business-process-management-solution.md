---
title: ビジネス プロセス管理ソリューションで効率的に SSO を使用して |Microsoft Docs
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
ms.openlocfilehash: eda9b88ceb99e6487562ecc03f8f7009b09f533e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321676"
---
# <a name="using-sso-efficiently-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションで SSO の効率的な使用
サービス指向ソリューションと同様には、ビジネス プロセス管理ソリューションは、注文処理ステージの数などの構成値を格納するのにエンタープライズ シングル サインオン (SSO) を使用します。 BizTalk がインストールされているときに存在するため、シークレット ストアを使用して、SSO が構成情報をキャッシュできるように、値はすぐに使用して、データベース接続文字列やパスワードなどの情報を保護できます。 これらの理由からすべては、シングル サインオンでした。 バックエンド アプリケーションへの接続を管理するため使用されている場合でものシークレット ストアは構成情報のことをお勧めします。  
  
 待機時間を減らすためには、ソリューションは構成値のローカル キャッシュを使用します。 ソリューションは、5 分ごとにキャッシュを更新します。  
  
 このトピックでは、ソリューションで使用されるキャッシュ メカニズムについて説明します。 このソリューションでは、SSO のキャッシュ サービス指向ソリューションよりも若干異なるアプローチを採用します。 サービス指向のソリューションの説明には、SSO 値がキャッシュを参照してください[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)します。  
  
## <a name="caching-configuration-values-locally"></a>ローカル キャッシュの構成値  
 ビジネス プロセス管理ソリューションでは、SSO 値へのアクセスを提供するのにシングルトン オブジェクトのプロパティを使用します。  
  
> [!NOTE]
>  シングルトン オブジェクトがオブジェクト インスタンスの 1 つだけ持つことができますを思い出してください。 単一オブジェクトとで作成の詳細についてはC#を参照してください[ http://go.microsoft.com/fwlink/?LinkId=58806](http://go.microsoft.com/fwlink/?LinkId=58806)します。  
  
 ソリューションでは、オーケストレーションは最初シングルトン オブジェクトを取得し、オブジェクトのプロパティから値を参照します。 コードをここでは、 **OrderManager**オーケストレーション。  
  
```  
configData = Microsoft.Samples.BizTalk.SouthridgeVideo.Utilities  
                .SsoConfigHelper.Singleton;  
numStages = configData.TotalStages;  
```  
  
 オーケストレーションの呼び出し、**シングルトン**メソッドを**SsoConfigHelper**オブジェクトの 1 つのコピーへのアクセスを取得するオブジェクト。 手の形でオブジェクトが、オーケストレーションは処理ステージの数を取得**TotalStages**します。  
  
 ソリューションに依存する一般的なシングルトンを作成する方法: コンス トラクターをプライベートには、オブジェクト自体のインスタンスを作成し、秘密の変数に割り当てることと、メソッドまたはプロパティからその変数の値へのアクセスを提供します。 **SsoConfigHelper**オブジェクトは、プロパティを使用して**シングルトン**、それ自体の 1 つのコピーへのアクセスを提供します。  
  
> [!NOTE]
>  **SsoConfigHelper**オブジェクトは、SSO のキャッシュから初期値を取得し、更新メカニズムを設定する静的コンス トラクターを使用します。 静的コンス トラクターが呼び出されることはできません、ため、シングルトン設計が保持されます。 静的コンス トラクターの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=59142](http://go.microsoft.com/fwlink/?LinkId=59142)します。  
  
 直接的または間接的にするかどうか、オーケストレーションで参照するすべてのオブジェクトをシリアル化する必要があります。 詳細については、「シリアル化」を参照してください[永続性とオーケストレーション エンジン](../core/persistence-and-the-orchestration-engine.md)します。 ただし、 **SsoConfigHelper**オブジェクトが、それでもオーケストレーション必要オブジェクトの 1 つ、現在のインスタンスを使用すると、エンジンでオーケストレーションを退避する場合、必ずしも serializable。 シリアル化と BizTalk Server 変数の詳細については、次を参照してください。[オーケストレーション変数の型](../core/orchestration-variable-types.md)します。  
  
> [!NOTE]
>  サービス指向ソリューション内のオブジェクトのすべてのパブリック メソッドは静的です。 したがって、オーケストレーションは、インスタンスを割り当てる変数にする必要はありませんし、クラスをシリアル化する必要はありません。  
  
 **SsoConfigHelper**オブジェクトでは、同じメカニズムを使用して取得し、サービス指向ソリューションのように構成値を更新します。 同じパターンのロックが使用されます。 これらのメカニズムの詳細については、次を参照してください。[を使用して SSO の効率的なサービス指向ソリューションで](../core/using-sso-efficiently-in-the-service-oriented-solution.md)のソース コードと**SsoConfigHelper**します。  
  
 ビジネス プロセス管理ソリューションを実装するサービス指向ソリューションでのキャッシュでシングル サインオン実行と同様に、 **IPropertyBag**からインターフェイス、 **Microsoft.BizTalk.SSOClient.Interop**値を格納する名前空間。 ビジネス プロセス管理ソリューションを使用して、 **HybridDictionary**オブジェクトではなく**NameValueCollection**オブジェクト。  
  
 ビジネス プロセス管理ソリューションでは、サービス指向ソリューションとは異なり、構成データに対応するプロパティを持つオブジェクトを公開します。 これには、オーケストレーションからメッセージの種類の違いを処理することができないようにします。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の重要なポイント](../core/implementation-highlights-of-the-business-process-management-solution.md)