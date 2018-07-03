---
title: アダプター デザイン時の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5e7b63c-6e17-4c54-9bbf-6964668a2420
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 815690aee7178db52936e8f1aca5641d1be945b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987371"
---
# <a name="adapter-design-time-configuration"></a>アダプターのデザイン時構成
アダプターには、実行時コンポーネントとデザイン時コンポーネントの両方が含まれます。 実行時コンポーネントを表示することはできません。 実行時コンポーネントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージの送信、受信、および処理をユーザーに意識させることなく行います。  
  
 アダプターのデザイン時コンポーネントは、管理ユーザー インターフェイスで表示できます。 デザイン時コンポーネントは、使用可能なプロパティの表示、管理入力の受け付け、およびアダプターを構成するための入力の検証を行います。 デザイン時コンポーネントでは、アダプターのプロパティを適切に構成して、実行時機能でメッセージを正しく交換できるようにすることが重要です。  
  
 ここでは、アダプターのデザイン時コンポーネントについてのみ説明します。 したがって、アダプターの構成を表示して設定する方法を中心に説明します。 アダプターを構成するには、次の 2 つの方法があります。  
  
- **プロパティ ブラウザー。** アダプターのプロパティを送信または受信ポート、または送信または受信ハンドラーを使用してプロパティ メニューで構成されている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 これらのアイテムの構成時に、プロパティ ブラウザーを使用してアダプター (トランスポート) を選択し、そのプロパティを構成します。 適用できるプロパティは、スキーマをとおしてセット名と共に表示されます。 たとえば、送信ハンドラーであれば、プロパティは TransmitHandler.xsd ファイルに格納され、受信場所であれば、プロパティは ReceiveLocation.xsd ファイルに格納されます。  アダプターの実装、 **IAdapterConfig**インターフェイスを特定し、プロパティ ブラウザー内の特定のプロパティを公開する適切なスキーマを読み込みます。 **IAdapterConfigValidation**インターフェイスはこれらのエントリを検証し、構成データを保存する前に、値に最終的な変更を加えるに使用します。  
  
- **アダプター メタデータのウィザードを追加します。** アプリケーションやデータベース アダプターの場合で BizTalk プロジェクトにアダプターに必要なメッセージの種類とポートの種類を記述するサポート スキーマをインポートする必要があります[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 それ以外に、アダプターで提供されるサービスの使用が必要になることもあります。 アダプター メタデータの追加ウィザードでは、アダプターがサポートするサービスを表示して、関連するメッセージの種類やポートの種類をプロジェクトにインポートできます。 このプロセスは、"メタデータ収集" と呼ばれます。 アダプター開発者サービスを記述する XML ファイルを作成し、ウィザードにいずれかでデザイン時に公開、 **IStaticAdapterConfig**または**IDynamicAdapterConfig**インターフェイスを使用次の結果:  
  
  -   **静的アダプター。** 。ウィザードは、アダプターのサービスの表示に使用する標準の既定階層ツリー構造を提供します。 静的アダプターとは、ウィザードで提供される標準ツリー ユーザー インターフェイス (UI) を使用するアダプターのことです。 使用して、 **IStaticAdapterConfig.GetServiceOrganization**と**GetServiceDescription** BizTalk プロジェクトに追加する選択したサービスを許可するメソッド。 これは、アダプター開発者にとって最も簡単な構成オプションですが、表示書式の厳密さはありません。  
  
  -   **動的アダプター。** 。ウィザードで提供される基本的なサービス選択の UI にニーズを満たすほどの柔軟性がない場合は、ウィザードで動的に表示されるカスタム UI を作成できます。 使用して、 **IDynamicAdapterConfig.DisplayUI** BizTalk プロジェクトに追加するサービスの選択を許可するカスタム UI を表示するメソッド。  
  
  ここでは、静的な方法または動的な方法のいずれかでデザイン時構成を処理するための 2 組のガイドラインを提供します。  
  
  Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソフトウェア開発キット (SDK) に含まれているサンプル ファイル アダプターをテンプレートとして使用して、独自のアダプターのデザイン時構成ソリューションを作成し、カスタマイズすることができます。 サンプル ファイル アダプターに関する注意とリファレンスが、デザイン時構成に関する各トピックで提供されており、独自のカスタム アダプター構成の要件を変更するのに役立ちます。 これらのガイドラインについての理解を深めるため、SDK に用意されているサンプル ファイル アダプターをインストールし、ビルドして実行することをお勧めします。 参照してください[ファイル アダプター (BizTalk Server サンプル)](../core/file-adapter-biztalk-server-sample.md)詳細についてはします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [静的デザイン時アダプター構成](../core/static-design-time-adapter-configuration.md)  
  
-   [動的デザイン時アダプター構成](../core/dynamic-design-time-adapter-configuration.md)  
  
-   [アダプター構成スキーマ](../core/adapter-configuration-schemas.md)  
  
-   [アダプター WSDL ファイル](../core/adapter-wsdl-files.md)  
  
-   [アダプターの GetSchema メソッド](../core/adapter-getschema-method.md)  
  
-   [アダプターの登録ファイル](../core/adapter-registration-file.md)  
  
-   [BizTalk Server へのアダプターのインストール](../core/install-the-adapter-into-biztalk-server.md)  
  
-   [アダプター プロジェクトのビルドおよびテスト](../core/build-and-test-the-adapter-project.md)