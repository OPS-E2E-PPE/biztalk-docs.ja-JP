---
title: Business Adapter SDK の Windows Communication Foundation の行とは |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc690e8f-fd37-44b5-a277-89952e631ae6
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3411785538e8dc6fcfe50cc2959b85481634264
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362616"
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>Business Adapter SDK の Windows Communication Foundation の行とは
機能とコンポーネントの概要については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 また、メタデータ、接続の管理、およびバインドとチャネルなど、知っておくべき用語を含む、主要な概念についても説明します。

## <a name="features-overview"></a>機能の概要
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]データと基幹業務システムの操作を公開するアダプターを構築する開発者のニーズを満たすために設計されました。 によって提供される機能の一部、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれます。  
  
- プロトコルのトランスポートとデータを公開するための一貫性のあるメカニズム
  
- WCF バインドとしてアダプターの公開
  
- WCF チャネル アーキテクチャによる拡張性
  
- [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
- 共通のメタデータの検索と参照ユーザー インターフェイスを使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] デザイン時の統合を使用して、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張機能は、次の機能を提供も、WCF に。  
  
- 既存の .NET Framework 通信テクノロジの統合
  
- ベンダー間相互運用性、信頼性、セキュリティ、トランザクションなどのサポート
  
- サービスの明示的な印刷の向き
  
## <a name="components-overview"></a>コンポーネントの概要
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプター開発者と、一連の実行時およびデザイン時コンポーネント、.NET オブジェクト モデル、およびサポートのコンポーネントを含むアダプターのコンシューマーの両方の一貫性のある反復可能なエクスペリエンスを提供します。  
  

|                                        コンポーネント                                        |                                                                                                       説明                                                                                                        |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]        |         作成のステップ バイ ステップ ガイダンスを提供[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]内でプロジェクト[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]します。         |
|            [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]            |                                                   アダプターでは、インターネット インフォメーション サービス (IIS) をホストする Web プロジェクトを作成するステップ バイ ステップ ガイダンスを提供します。                                                    |
| [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 実行時のシステム |                          では、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF を拡張することによってチャネル アーキテクチャとその他のランタイム サービスを提供します。                           |
|  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] オブジェクト モデル   |                  クラス、型、およびメタデータの正規化、キャッシュ、接続の管理とプール、およびメッセージング検査など、アダプターの一般的なタスクをサポートしているインターフェイスのコレクション。                  |
|     [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]     |                               カスタム .NET アプリケーションを使用するには、アダプターを使用して開発を使用できます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。                                |
|    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]    | [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アダプターを使用して開発を実行するため、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 |

## <a name="sdk-fundamentals"></a>SDK の基礎  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム、Api、およびデータと基幹業務システムからの操作を公開するアダプターを作成するためのデザイン時ツールのコレクションで構成されます。 アダプターはアダプターのコンシューマーと基幹業務システム間でメッセージを管理し、メタデータ、データ、またはその他の情報で構成できます。  

### <a name="metadata"></a>メタデータ  
 作成されたアダプターの特徴の 1 つ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]メタデータは、1 つの Windows Communication Foundation (WCF) サービス モデルのオブジェクト モデルを使用して実装されているとします。 メタデータは、データ、操作、プロパティ、およびシステムの他の動的な特性について説明し、アダプターのコンシューマーを検出、使用、およびターゲット システムと通信するために使用します。  

 一般的な WCF サービス プログラミング ライフ サイクルには、作成して、サービスをホストする WCF サービスの開発者が含まれています。 WCF サービスのエンドポイントから、アドレス、バインディング、およびコントラクトを成る WCF の「A、B、および C の」とも呼ばれます。  アドレスは、サービスの場所は、プロトコルおよびサービスと通信するために使用するトランスポート バインディングを指定します。  WCF サービスの開発者は、WCF System.ServiceModel オブジェクト モデルを使用してコントラクトを定義、WCF サービスでは、形式でその実装を提供し、ServiceHost を使用してをホストします。 SvcUtil.exe や[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公開されたサービスのメタデータに対応するクライアントを構築するために使用できます。 サービスが稼働するいると、好きな言語と WCF サービスの詳細に対応するクライアントの実装用に app.config ファイルで、WCF プロキシを生成するサービス エンドポイントのアドレスに対して、デザイン時ツールを実行できます。  

 WCF LOB アダプター開発者は、一方で提供されるメタデータ オブジェクト モデルを実装、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]操作と、アダプターでサポートされる型を定義します。 送信アダプターは、WCF カスタム バインドであるため、コンシューマー アプリケーション内でインプロセスでホスト型になります。  コンピューターでは、アダプターがインストールされると[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照し、メタデータを検索して、その結果、アダプター構成の詳細を含む app.config ファイルと共に任意の言語で、WCF プロキシを生成するために使用できます。 コントラクトが作成され、基幹業務システムで使用できるライブ メタデータのクエリを実行して、WCF LOB アダプターによってオンデマンドを生成します。  

 たとえば、基幹業務システムは adjudicate 医療費請求のさまざまな種類の可能性があり、増大する一意の操作、データ型、ビジネス ルール、およびシステムのユーザーによって作成されたレポートのコレクションを含めることができます。 この情報が静的コントラクトとして公開されている場合は、新しいビジネス オブジェクトがシステムに追加されるか、単に新しいビジネス オブジェクトへのアクセスを提供しないとして変更するがあります。 ただし、クレーム裁定システム内で動的なビジネス オブジェクトに関する情報が参照可能な (および検索可能な) の場合は、制度化された要求または新しいレポートを新しい検証規則などの新しいオブジェクトが公開される、消費されることができます。  

### <a name="connection-management"></a>接続の管理  
 情報は、基幹業務システムと交換されることができます、前に、アダプターは接続を確立する必要があります。 接続、基幹業務システム (プロバイダー) にアダプター (コンシューマー) をリンクを開く、終了、中止、および接続の有効性の確認を含む接続のライフ サイクルを制御します。 基幹業務システムの要件に基づき、資格情報とサーバー名、既定のディレクトリ、またはポート番号などの接続パラメーターの 1 つまたは複数の接続が必要です。  

 接続の有効期間は、接続プールによって管理されます。 アダプターは、新しい接続を要求すると、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]には、既存の接続を 1 つの場合は、それ以外の使用可能な新しい接続を作成し、プールに配置、アダプターに提供されます。 アダプターが接続を完了するとは、プールに配置されます。 特定のしきい値を超えてアイドル状態の接続が閉じられ、プールから削除します。  

### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の拡張機能は、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、マネージ コードを使用したサービス指向アプリケーションを構築するための統一プログラミング モデル。 アダプターを使用して記述、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]として表示された[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]WCF 対応アプリケーションで使用できるバインドです。  

## <a name="important-terms"></a>重要な用語  

|           |                                                                                                                                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  バインド  | アダプターとの通信方法を定義します。 バインディングがによって作成された、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]し、トランスポート、エンコーディング、およびその他の詳細を定義します。 バインディングの 1 つまたは複数のバインド要素が可能性があります。 |
|  channel  |                                                          バインド要素の実装です。 チャネル スタックを作成するのには相互にバインド スタックのチャネルのコレクション。                                                           |
|  メッセージ  |                                                                              本文やヘッダーなど、いくつかの要素で構成されるデータの自己完結型の単位。                                                                              |
| メタデータ (metadata)  |                                                                   操作と利用可能なデータを含む、基幹業務システムの特性について説明します。                                                                    |
| operation |                             関数と基幹業務システムによって公開されるメソッド。 データを操作また adjudicating クレームや、注文を作成する売上データの照会などの便利なアクティビティを実行します。                              |
   
## <a name="see-also"></a>参照  
 [BizTalk Server と WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [WCF LOB アダプター SDK のチュートリアル](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)