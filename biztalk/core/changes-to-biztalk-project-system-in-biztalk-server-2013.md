---
title: BizTalk Server 2013 での BizTalk プロジェクト システムの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82f0dd18-073c-4cba-aa0d-48076c58f874
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 836ffa11e3b15b379b8f4a07def2269f0f29a453
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006275"
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a>BizTalk Server 2013 での BizTalk プロジェクト システムへの変更
このトピックでは変更の概要を BizTalk Server で BizTalk プロジェクト システムにします。  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a>プロジェクト プロパティがプロジェクト デザイナー ウィンドウに表示される  
 BizTalk Server プロジェクトのプロパティは、プロパティ ダイアログ ボックスではなく、Visual Studio のプロジェクト デザイナーに表示されるようになりました。 プロジェクト デザイナーは、プロジェクトのプロパティ、設定、およびリソースを管理するための一元的な場所を提供します。 プロジェクト デザイナーは、フォーム デザイナーやクラス デザイナーと同じように、Visual Studio IDE の単一のウィンドウとして表示され、左側のタブを通じてアクセスできる多数のページを含みます。 詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=190417](http://go.microsoft.com/fwlink/?LinkId=190417)です。  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a>スキーマ ファイルおよびマップ ファイルのプロパティがプロパティ ウィンドウに表示される  
 などのスキーマおよびマップ ファイルのプロパティを**入力インスタンス ファイル名**と**テスト マップ入力インスタンス**プロパティ ウィンドウでの代わりに、個別に表示される**のプロパティ**  ダイアログ ボックス。  
  
## <a name="add-web-reference-option-on-projects"></a>プロジェクトの [Web 参照の追加] オプション  
 **Web 参照の追加**オプションは、プロジェクト名を右クリックしたときに使用できませんまたは**参照**ソリューション エクスプ ローラー。 Web サービス (.asmx) への Web 参照を追加するには、次の手順を実行します。  
  
1.  右クリック**参照**をクリックして、プロジェクト**サービス参照の追加**です。  
  
2.  **サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**です。  
  
3.  **サービス参照設定**ダイアログ ボックスで、をクリックして**Web 参照の追加**です。  
  
4.  URL を入力し、をクリックして**移動**です。  
  
5.  をクリックして**参照の追加**Web 参照を追加します。  
  
    > [!TIP]
    >  BizTalk プロジェクトに Web 参照を追加した後、 **Web 参照の追加**メニュー オプションは、参照、Web 参照およびプロジェクト ノードを使用します。  
  
 サービスおよび Web 参照の追加に関する詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131577](http://go.microsoft.com/fwlink/?LinkId=131577)です。  
  
## <a name="msbuild-integration"></a>MSBUILD の統合  
 Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージ プロジェクトに関するビルド情報を保存します。 詳細については、次を参照してください。 [Visual Studio での MSBUILD 統合](../core/msbuild-integration-with-visual-studio.md)です。  
  
## <a name="team-foundation-server-integration"></a>Team Foundation Server の統合  
 BizTalk プロジェクトのソース制御システムとして Team Foundation Server を使用できます。 チェックインやチェックアウトなどの操作を [ソリューション エクスプローラー] ウィンドウ自体から実行できます。  
  
## <a name="support-for-unit-testing"></a>単体テストのサポート  
 この機能を使用すると、スキーマ、マップ、およびパイプラインの単体テストを実行できます。 詳細については、次を参照してください。 [BizTalk Server プロジェクトによる単体テスト](../core/unit-testing-with-biztalk-server-projects.md)です。  
  
## <a name="debug-map-feature"></a>マップ機能のデバッグ  
 **マップ機能のデバッグ**です。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のインライン XSLT デバッガーを使用して、マップ (XSLT) をデバッグできます。 詳細については、次を参照してください。[マップのデバッグ方法](../core/how-to-debug-maps.md)です。  
  
## <a name="migrating-biztalk-server-projects"></a>BizTalk Server プロジェクトの移行  
 Visual Studio プロジェクトが以前のバージョンの用に開発された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Visual Studio 変換ウィザードを使用して、BizTalk Server 環境に移行できます。 詳細については、次を参照してください。 [BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)です。  
  
## <a name="release-and-debug-build-types"></a>リリース ビルドとデバッグ ビルドの種類  
 BizTalk プロジェクトに 2 つのビルドの種類があるようになりました:**リリース**と**デバッグ**、どの置換**開発**と**展開**の前バージョン。 ただし、引き続きを参照してください、**開発**と**展開**から移行されるプロジェクトの構成[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]です。  
  
## <a name="embedding-tracking-and-debugging-information"></a>追跡情報とデバッグ情報の埋め込み  
 **追跡情報の埋め込み**と**デバッグ情報の生成**は出力構成プロパティに置き換え、**定数 TRACE の定義**と**DEBUG 定数の定義**ビルド オプション、**ビルド**プロジェクト デザイナーのタブです。 **BPEL 互換コードの生成**構成プロパティが置き換え**BPEL 互換コードの生成**プロジェクト プロパティ ウィンドウでプロパティです。  
  
> [!IMPORTANT]
>  Visual Studio 変換ウィザードでは、これらの設定が新しい環境に自動的に移行されます。  
  
## <a name="user-access-control"></a>ユーザー アクセス制御  
 Visual Studio では、管理者特権で Visual Studio を実行しない限り、ユーザー アクセス制御 (UAC) 機能が有効になったコンピューター上に BizTalk プロジェクトを展開できません。 管理者特権で Visual Studio を実行する をクリックして**開始**、 をポイント**すべてのプログラム**、指す**Microsoft Visual Studio**を右クリックして**Microsoft Visual Studio\<バージョン\>**、クリックして**管理者として実行**です。  
  
## <a name="c-files-in-a-biztalk-project"></a>BizTalk プロジェクトの C# ファイル  
 BizTalk Server では、柔軟なパッケージに行うのための BizTalk アイテムとヘルパー クラスを結合することができます。  ただしを使用して直接新しい c# ファイルを追加することはできません、**新しい項目の追加**または**新しいクラスの追加**メニュー オプション。  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a>GenerateCSFiles レジストリ キーの廃止  
 **GenerateCSFiles**レジストリ キーは廃止されます。 生成されたすべての .cs ファイルは、[ソリューション エクスプローラー] ウィンドウに表示されます。 をクリックする必要があります **[すべてのファイル**ツールバー項目では、ソリューション エクスプ ローラー] ウィンドウで、一部の BizTalk アイテムに関連付けられた .cs ファイルを参照してください。