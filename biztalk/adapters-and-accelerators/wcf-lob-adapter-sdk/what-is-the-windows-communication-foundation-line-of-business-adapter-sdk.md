---
title: ビジネス アダプター SDK の Windows Communication Foundation 回線とは |Microsoft ドキュメント
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
ms.openlocfilehash: 084201d9680cb8d17c37c2218ebe7622c4cc4495
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226490"
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>ビジネス アダプター SDK の Windows Communication Foundation 回線とは
コンポーネントおよび機能の概要については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 また、メタデータ、接続の管理を調べるには、バインドとチャネルなどの条件など、主要な概念についても説明します。

## <a name="features-overview"></a>機能の概要
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]データと基幹業務システムの操作を公開するアダプターを構築する開発者のニーズを満たすように設計されました。 によって提供される機能の一部、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]が含まれます。  
  
-   一貫性のあるプロトコルのトランスポートとデータを公開するしくみ
  
-   WCF バインドとして、アダプターの公開
  
-   WCF チャネル アーキテクチャを機能拡張
  
-   [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
-   共通のメタデータの検索と参照 ユーザー インターフェイスを使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]デザイン時の統合を使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]拡張機能は、次の機能を提供も、WCF に。  
  
-   既存の .NET Framework 通信テクノロジの統合
  
-   仕入先の間の相互運用性、信頼性、セキュリティ、トランザクションなどのサポート
  
-   明示的なサービス印刷の向き
  
## <a name="components-overview"></a>コンポーネントの概要
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプター開発者と一連の実行時およびデザイン時コンポーネント、.NET オブジェクト モデル、およびサポート コンポーネントを含むアダプター コンシューマーの両方に対して、一貫性のある、反復可能なエクスペリエンスを提供します。  
  
|コンポーネント|Description|  
|---------------|-----------------|  
|[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]|作成の詳細な手順のガイダンスを提供[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]内でプロジェクト[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]です。|  
|[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]|インターネット インフォメーション サービス (IIS) でのアダプターをホストする Web プロジェクトを作成する詳細な手順について説明します。|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]実行時のシステム|では、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF の拡張によってチャネル アーキテクチャとその他の実行時のサービスを提供します。|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]オブジェクト モデル|クラス、型、およびメタデータの正規化、キャッシュ、接続の管理とプール、およびメッセージング検査などの一般的なアダプター タスクをサポートするインターフェイスのコレクション。|  
|[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]|により、カスタム .NET アプリケーションを使用して開発されたアダプターを使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。|  
|[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して開発されたアダプターを利用できるよう、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。|  

## <a name="sdk-fundamentals"></a>SDK の基礎  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム、Api、およびデータと基幹業務システムからの操作を公開するアダプターを作成するためのデザイン時ツールのコレクションで構成されます。 アダプターは、アダプターのコンシューマーおよび基幹業務システム間でメッセージを管理し、メタデータ、データ、またはその他の情報で構成できます。  
  
### <a name="metadata"></a>メタデータ  
 記述されたアダプタの特性の 1 つ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]メタデータは、いずれかの Windows Communication Foundation (WCF) サービス モデルのオブジェクト モデルを使用して実装されているとします。 メタデータは、データ、操作、プロパティ、およびシステムの他の動的な特性について説明し、検出、使用、および対象システムとの対話にアダプターのコンシューマーによって使用されます。  
  
 一般的な WCF サービス プログラミング ライフ サイクルには、作成して、サービスをホストしている WCF サービスの開発者が含まれています。 WCF サービスのエンドポイントは、アドレス、バインディング、およびコントラクトが WCF の「A、B、および C の」とも呼ばれます。  アドレスは、バインディング プロトコルと、サービスと通信するために使用されるトランスポートを指定するときに、サービスの場所です。  WCF サービスの開発者は、WCF System.ServiceModel オブジェクト モデルを使用してコントラクトを定義、WCF サービスの形式でその実装を提供し、ServiceHost を使用することをホストします。 SvcUtil.exe または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]公開されたサービスのメタデータに対応するクライアントを構築するために使用できます。 サービスが起動して稼働すると、使用する言語と WCF サービスの詳細に対応するクライアントの実装用に app.config ファイルで、WCF プロキシを生成するサービス エンドポイントのアドレスに対して、デザイン時ツールを実行できます。  
  
 WCF LOB アダプター開発者は、その一方で、モデルを実装して、メタデータ オブジェクトで提供される、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]操作と、アダプターによってサポートされる型を定義します。 送信アダプターが WCF カスタム バインドのため、コンシューマー アプリケーション内でインプロセスでホスト型です。  コンピューターでは、アダプターがインストールされる[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照して、メタデータを検索し、その結果をアダプター構成の詳細を含む app.config ファイルと選択した言語で、WCF プロキシを生成するために使用できます。 コントラクトが作成され、基幹業務システムで使用できるライブのメタデータのクエリを実行して、オンデマンドで WCF LOB アダプターを生成します。  
  
 たとえば、基幹業務システムでは、医療費請求の種類を adjudicate 可能性があり、一意の操作、データ型、ビジネス ルール、およびシステムのユーザーによって作成されたレポートの増大するコレクションを含めることがあります。 この情報が、静的なコントラクトとして公開されている場合、新しいビジネス オブジェクトがシステムに追加されるか、単に新しいビジネス オブジェクトへのアクセスを提供できませんとして変更するがします。 ただし、クレーム裁定システム内でのダイナミックなビジネス オブジェクトに関する情報が参照可能な (および検索) の場合は、新しいオブジェクトに新しい検証規則制度化された要求または新しいレポートをなどが公開されるされ、利用できます。  
  
### <a name="connection-management"></a>接続の管理  
 基幹業務システムで情報を交換することができます、前に、アダプターは接続を確立する必要があります。 接続は、基幹業務システム (プロバイダー) にアダプター (消費者) をリンクし、開く、終了、中止、および接続の有効性を確認するをなど、接続のライフ サイクルを制御します。 基幹業務システムの要件に基づき、資格情報とサーバー名、既定のディレクトリ、またはポート番号などの接続パラメーターの 1 つまたは複数の接続が必要です。  
  
 接続の有効期間は、接続プールによって管理されます。 アダプターで新しい接続が要求されたときに、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]場合は 1 つの既存の接続が利用可能な場合、新しい接続が作成し、プールに配置され、アダプターに提供しを提供します。 アダプターでは、接続処理が終わったらプールに配置されます。 特定のしきい値を超えてアイドル状態の接続が閉じています。 プールから削除します。  
  
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の拡張機能は、 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]、マネージ コードを使用してサービス指向アプリケーションを構築するための統一されたプログラミング モデルです。 アダプターを使用して記述、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]として表示された[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]WCF 対応アプリケーションで使用できるバインドです。  
  
## <a name="important-terms"></a>重要な用語  

| | |
|---|---|
| バインド (binding) | アダプターとの通信方法を定義します。 バインディングがによって作成された、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]し、トランスポート、エンコーディング、およびその他の詳細を定義します。 バインディングの 1 つまたは複数のバインド要素が可能性があります。 |
|channel | バインド要素の実装です。 チャネル、チャネル スタックを作成するために互いの上に、バインド スタックのコレクションです。 |
| message  |  本文やヘッダーなど、いくつかの要素で構成されるデータの自己完結型の単位。|
| メタデータ (metadata) | 操作と使用可能なデータを含む、基幹業務システムの特性について説明します。|
| operation | 関数と基幹業務システムによって公開されるメソッド。 これらは、データを操作し、adjudicating 信頼性情報、注文を作成する、売上データの照会などに便利ですの作業を実行します。  |
 
   
## <a name="see-also"></a>参照  
 [BizTalk Server と WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [WCF LOB アダプター SDK のチュートリアル](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)