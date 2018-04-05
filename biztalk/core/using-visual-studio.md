---
title: Visual Studio の使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio
ms.assetid: 1ef68df2-5205-4d96-9e0f-0ae78800a121
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b48f5aca0bd1e5c17d942e332f7f3d223d752b67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-visual-studio"></a>Visual Studio の使用
BizTalk プロジェクト システム内では、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の多くのツールを使用できるほか、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上で動作するアプリケーションの作成専用に設計されたツールも使用できます。 ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で動作するアプリケーションの作成に使用できる、共通の手順をいくつか説明します。  
  
 BizTalk プロジェクト システムでは、ソリューション エクスプローラー、プロパティ ウィンドウなど、統一の取れた多くのユーザー インターフェイス (UI) を使用して、アプリケーションを作成できます。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールすると使用可能になる BizTalk エディターなどのコンポーネントがあります。 これらの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 固有の UI コンポーネントはあらゆるプロジェクト システムで使用できますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で動作するアプリケーションの構築に特に有効です。  
  
 BizTalk プロジェクト システムでは、他の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト システムと同じメニューやメニュー コマンドが多く使われていますが、新しいコマンド、使用できないコマンド、機能が拡張されているコマンド、および機能が制限されているコマンドも一部あります。 ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で使用できるさまざまなメニュー、およびこれらのメニューと BizTalk プロジェクト システムとの連携方法について説明します。  
  
> [!NOTE]
>  以下のトピックでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] と動作が異なるメニューおよびメニュー項目に焦点を当てて説明します。  
  
## <a name="file-menu"></a>[ファイル] メニュー  
 ほとんどの**ファイル**メニュー コマンドの動作とその他の BizTalk プロジェクトに対して同じ方法[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクト。 BizTalk プロジェクトを操作している場合にサポートされない (使用できない) コマンドがあります。 たとえば、**印刷**パイプラインを使用しているときに、コマンドがサポートされていません。  
  
## <a name="view-menu"></a>[表示] メニュー  
 次の表は、BizTalk プロジェクト システム ウィンドウ、ツールバー、およびツールボックスから使用可能な**ビュー**メニュー。  
  
|サブメニュー名|サブメニュー名 (該当する場合)|Description|  
|------------------|------------------------------------|-----------------|  
||||  
|**他のウィンドウ**|**オーケストレーションの種類**|[オーケストレーションの種類] ウィンドウは、オーケストレーション パラメーター、ポート、ポートの種類、メッセージやマルチパート メッセージの種類、関連付けセットや関連付けの種類、ロール リンクやロール リンクの種類、スコープ、およびオーケストレーションのプロパティの追加、削除、検証を行えるウィンドウです。 **注:**このウィンドウは、開いたオーケストレーションから利用できるのみです。|  
|**他のウィンドウ**|**式エディター**|[式エディター] ウィンドウは、複雑な式を入力できる IntelliSense を備えた標準の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] テキスト エディターを表示するウィンドウです。|  
|**[ツールボックス]**|**BizTalk パイプライン コンポーネント**|これは、パイプラインのデザイン画面にドラッグできるパイプライン コンポーネントの一覧です。 使用できるパイプライン コンポーネントをアクティブなパイプラインに追加することのみが可能です。|  
|**[ツールボックス]**|**BizTalk オーケストレーション**|これは、オーケストレーションのデザイン画面にドラッグできるオーケストレーション図形の一覧です。|  
|**[ツールボックス]**|**BizTalk マッパー**|これは、マップのグリッド画面にドラッグできる Functoid の一覧です。 Functoid は、機能ごとにグループ化されています。|  
|**[ツール バー]**|**BizTalk エディター**|構造化されたドキュメント スキーマを簡単に作成するためのビジュアル ツールです。これらのスキーマは、XSD (XML Schema definition) 言語で指定します。また、XML 形式および XML 以外の形式のどちらにも対応させることができます。|  
|**[ツール バー]**|**BizTalk マッパー**|BizTalk エディターで作成された 2 つのスキーマに基づいて、XML ドキュメントの変換を簡単に指定するための GUI ツールです。コンパイル後の出力として、XSLT (Extensible Stylesheets Language Transformations) スタイル シートが生成されます。|  
  
## <a name="project-menu"></a>[プロジェクト] メニュー  
 次の表のコマンドの一部で、**プロジェクト**メニュー。  
  
|サブメニュー名|Description|  
|------------------|-----------------|  
|**参照を追加します。**|他のプロジェクト、.NET プロジェクト、または COM プロジェクトを参照するときに使用します。|  
|**サービス参照を追加します。**|WCF サービス参照を追加するときに使用します。 使用することも、この項目をクリックして Web 参照を追加する**詳細**上、**サービス参照の追加** ダイアログ ボックス。|  
|**生成された項目を追加します。**|生成済みのアダプターまたはスキーマ ファイルを追加するか、WCF サービスを使用するときに使用します。|  
|**アダプター サービス参照を追加します。**|このメニュー項目を使用して、メタデータの参照 (および検索)、および選択した操作と種類に応じた .NET CLR プロキシ クラスを生成します。 **注:**この項目で BizTalk メニューの場合にのみに少なくとも 1 つのアダプターが表示されます (に付属して[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) がコンピューターにインストールされています。|  
|**追加アダプター参照**|このメニュー項目を使用して、アダプターからのメタデータの参照 (および検索)、および選択した操作に応じた XML スキーマを生成します。 **注:**この項目で BizTalk メニューの場合にのみに少なくとも 1 つのアダプターが表示されます (に付属して[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) がコンピューターにインストールされています。|  
  
 BizTalk Web サービスの Web 参照を追加する方法については、次を参照してください。 [Web 参照を追加する](../core/adding-web-references.md)です。  
  
## <a name="build-menu"></a>[ビルド] メニュー  
 **ビルド**メニューには、ビルド コマンドが含まれています。 実行するコマンドも含まれています。 **Configuration Manager**をビルドおよび配置の構成オプションを設定します。 プロジェクトを配置するには、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして、**展開**コマンド。 この展開方法は、アプリケーションの開発時または単純なシナリオでのみ適用できます。 この展開方法は**いない**バージョンを追跡し、簡単に以前のバージョンのアセンブリを上書きすることができます。 実稼働環境ではなく、開発フェーズやテスト フェーズでは、同じバージョンの再利用が必要になる場合もあります。 展開については、次を参照してください。 [Understanding BizTalk アプリケーションの展開と管理](../core/understanding-biztalk-application-deployment-and-management.md)です。  
  
 BizTalk アイテムを BizTalk 管理データベースに追加するには、アセンブリ展開ウィザードを実行します。 アセンブリ展開ウィザードの詳細については、次を参照してください。[を Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)です。  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] には、コンパイル済みのアセンブリを受け取ってそれを難読化するバージョンの Dotfuscator が組み込まれており、シンボルおよび他の識別子の名前を変更して知的所有権を保護します。 このツールをとおして実行されたアセンブリは展開できません。  
  
## <a name="debug-menu"></a>[デバッグ] メニュー  
 BizTalk プロジェクト システムをサポートしている、**デバッグ**メニュー コマンド。 デバッグについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[オーケストレーションのデバッグ](../core/debugging-orchestrations.md)です。  
  
## <a name="biztalk-menu"></a>[BizTalk] メニュー  
 プロジェクトを操作する場合、 **BizTalk** BizTalk エディター、BizTalk マッパー、または BizTalk オーケストレーション デザイナーを開くときに、メニューが表示されます。 つまり、スキーマ、マップ、またはオーケストレーションを編集しようとすると、BizTalk メニューが表示されます。  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の他のプロジェクト システムからオーケストレーション デザイナー、BizTalk エディター、および BizTalk マッパーにアクセスできますが、BizTalk ツールの動作は予測できないものになります。 オーケストレーション デザイナー、BizTalk エディター、BizTalk マッパーは、BizTalk プロジェクトのコンテキスト内部でのみ使用してください。  
  
## <a name="help-menu"></a>[ヘルプ] メニュー  
 次の表のコマンドの一部で、**ヘルプ**メニューに関連する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
|メニュー コマンド|Description|  
|------------------|-----------------|  
|**ダイナミック ヘルプを表示する**|このメニュー コマンドが表示されます、**ダイナミック ヘルプ**タスクに基づいて、タブのトピックを動的に生成します。|  
|**目次**|このメニュー コマンドが表示されます、**内容**タブし、インストールされているすべてのヘルプ コレクションを表示します。 これらのコンテンツを表示するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の製品ドキュメントがインストールされている必要があります。|  
|**Microsoft BizTalk Server について**|このメニュー コマンドが表示されます、 **Microsoft BizTalk Server に関する** ダイアログ ボックス。 このダイアログ ボックスには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の製品情報が表示されます。|  
|**Index**|このリリースの [キーワード] からは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のヘルプ ドキュメントにアクセスすることはできません。|  
|**検索**|フィルターがない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ ドキュメントを選択する場合は、このリリースに**(フィルターなし)**で、**でフィルター処理された**ドロップダウン リスト、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ ドキュメントがあります。検索します。|  
  
## <a name="property-pages"></a>プロパティ ページ  
 プロジェクト デザイナーのプロパティ ページを使用すると、アセンブリのプロジェクト プロパティを構成したり、BizTalk プロジェクトを展開するためのプロパティを構成したりできます。  
  
### <a name="procedures"></a>手順  
  
##### <a name="to-configure-assembly-project-properties"></a>アセンブリのプロジェクト プロパティを構成するには  
  
1.  ソリューション エクスプローラーで、プロジェクトを選択します。  
  
2.  **プロジェクト** メニューのをクリックして**プロパティ**プロジェクト デザイナーをアクティブにします。  
  
3.  クリックして、**アプリケーション**タブです。  
  
4.  をクリックして**アセンブリ情報**し、目的のアセンブリ プロパティを更新します。  
  
    > [!NOTE]
    >  使用して、**署名** タブで実行されているアプリケーションに証明書を使用している場合は、アセンブリのキー ファイルの場所を指定するプロジェクト デザイナーで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。  
  
##### <a name="to-configure-deployment-properties"></a>配置プロパティを構成するには  
  
1.  展開プロパティを構成するプロジェクトを選択します。  
  
2.  **プロジェクト** メニューのをクリックして**プロパティ**プロジェクト デザイナーをアクティブにします。  
  
3.  クリックして、**展開**タブし、展開プロパティを更新します。  
  
## <a name="see-also"></a>参照  
 [開発者用ツール](../core/developer-tools.md)