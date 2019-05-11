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
ms.openlocfilehash: 7f4cad6268e044adef1d9f94c84456d628a41fd4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361594"
---
# <a name="adapter-design-time-configuration"></a>アダプターのデザイン時構成
アダプターには、実行時とデザイン時コンポーネントの両方が含まれています。 実行時コンポーネントでは、ユーザーに表示されません。 送信、受信、および処理の担当に透過的に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ。  
  
 アダプターのデザイン時コンポーネントは、管理ユーザー インターフェイスで表示します。 使用可能なプロパティを表示する、管理用の入力を受け取ると、アダプタを構成するには、その入力を検証する責任を負います。 デザイン時コンポーネントがメッセージを正しく交換する実行時機能を有効にするアダプターのプロパティの適切な構成を許可することが重要です。  
  
 このセクションでは、アダプターのデザイン時コンポーネントのみについて説明します。 表示して、アダプターの構成を設定する方法を中心にしたがって予定です。 これには、アダプターを構成する 2 つの方法があります。  
  
- **プロパティ ブラウザー。** アダプターのプロパティを送信または受信ポート、または送信または受信ハンドラーを使用してプロパティ メニューで構成されている、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 これらの成果物の構成中に、アダプター (トランスポート) が選択されているし、プロパティ ブラウザーを使用してそのプロパティを構成します。 セットの名前を持つスキーマでは、適用可能なプロパティが表示されます。 たとえば、送信 (送信) ハンドラーのプロパティは TransmitHandler.xsd ファイルになります受信場所、ReceiveLocation.xsd ファイルになります。  アダプターの実装、 **IAdapterConfig**インターフェイスを特定し、プロパティ ブラウザー内の特定のプロパティを公開する適切なスキーマを読み込みます。 **IAdapterConfigValidation**インターフェイスはこれらのエントリを検証し、構成データを保存する前に、値に最終的な変更を加えるに使用します。  
  
- **アダプター メタデータのウィザードを追加します。** アプリケーションやデータベース アダプターの場合で BizTalk プロジェクトにアダプターに必要なメッセージの種類とポートの種類を記述するサポート スキーマをインポートする必要があります[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 または、アダプターによって提供されるサービスを使用する必要がある場合があります。 アダプター メタデータの追加ウィザードを使用すると、アダプターをサポートするサービスを表示し、関連するメッセージの種類とポートの種類をプロジェクトにインポートできます。 このプロセスは、「メタデータ収集」と呼ばれます。 アダプター開発者サービスを記述する XML ファイルを作成し、ウィザードにいずれかでデザイン時に公開、 **IStaticAdapterConfig**または**IDynamicAdapterConfig**インターフェイスを使用次の結果:  
  
  -   **静的アダプター。** ウィザードでは、アダプターのサービスを表示する標準の既定階層ツリー構造を提供します。 静的アダプターは、ウィザードによって提供される標準ツリー ユーザー インターフェイス (UI) を使用するアダプターとして定義されます。 使用して、 **IStaticAdapterConfig.GetServiceOrganization**と**GetServiceDescription** BizTalk プロジェクトに追加する選択したサービスを許可するメソッド。 これは、アダプター開発者にとって最も簡単な構成オプションですが、表示形式のさはありません。  
  
  -   **動的アダプター。** ウィザードによって動的に表示されるカスタム UI を作成する UI ニーズを満たす十分な UI、ウィザードによって提供される基本的なサービスの選択に柔軟性がない場合。 使用して、 **IDynamicAdapterConfig.DisplayUI** BizTalk プロジェクトに追加するサービスの選択を許可するカスタム UI を表示するメソッド。  
  
  ここでは、静的または動的な方法のいずれかでデザイン時構成を処理するためのガイドラインの 2 つのセットを示します。  
  
  Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK) には、使用できるサンプル ファイル アダプターが含まれています。 作成して、独自のアダプターのデザイン時構成ソリューションをカスタマイズするテンプレートとして。 サンプル ファイル アダプターに関する注意とリファレンスは、の各カスタム アダプター構成要件を変更するためのデザイン時構成トピックで提供されます。 次のガイドラインを理解するには、をインストールし、ビルドし、SDK で提供されているサンプル ファイル アダプターを実行する可能性があります。 参照してください[ファイル アダプター (BizTalk Server サンプル)](../core/file-adapter-biztalk-server-sample.md)詳細についてはします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [静的デザイン時アダプター構成](../core/static-design-time-adapter-configuration.md)  
  
-   [動的デザイン時アダプター構成](../core/dynamic-design-time-adapter-configuration.md)  
  
-   [アダプター構成スキーマ](../core/adapter-configuration-schemas.md)  
  
-   [アダプター WSDL ファイル](../core/adapter-wsdl-files.md)  
  
-   [アダプターの GetSchema メソッド](../core/adapter-getschema-method.md)  
  
-   [アダプターの登録ファイル](../core/adapter-registration-file.md)  
  
-   [BizTalk Server へのアダプターのインストール](../core/install-the-adapter-into-biztalk-server.md)  
  
-   [アダプター プロジェクトのビルドおよびテスト](../core/build-and-test-the-adapter-project.md)