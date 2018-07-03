---
title: BizTalk Server 2013 での BizTalk プロジェクト システムへの変更 |Microsoft Docs
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
ms.openlocfilehash: 1cf56be3eaf2e9601c7a92a293b422f9393a4efa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003403"
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a>BizTalk Server 2013 での BizTalk プロジェクト システムへの変更
このトピックではする BizTalk Server での BizTalk プロジェクト システムへの変更の概要を説明します。  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a>プロジェクト プロパティがプロジェクト デザイナー ウィンドウに表示される  
 BizTalk Server プロジェクトのプロパティは、プロパティ ダイアログ ボックスではなく、Visual Studio のプロジェクト デザイナーに表示されるようになりました。 プロジェクト デザイナーは、プロジェクトのプロパティ、設定、およびリソースを管理するための一元的な場所を提供します。 プロジェクト デザイナーは、フォーム デザイナーやクラス デザイナーと同じように、Visual Studio IDE の単一のウィンドウとして表示され、左側のタブを通じてアクセスできる多数のページを含みます。 詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=190417](http://go.microsoft.com/fwlink/?LinkId=190417)します。  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a>スキーマ ファイルおよびマップ ファイルのプロパティがプロパティ ウィンドウに表示される  
 などのスキーマとマップ ファイル プロパティ**入力インスタンス ファイル名**と**テスト マップ入力インスタンス**、プロパティ ウィンドウの代わりに、別に表示される**プロパティ**  ダイアログ ボックス。  
  
## <a name="add-web-reference-option-on-projects"></a>プロジェクトの [Web 参照の追加] オプション  
 **Web 参照の追加**オプションは、プロジェクト名を右クリックしてご利用いただけませんまたは**参照**ソリューション エクスプ ローラー。 Web サービス (.asmx) への Web 参照を追加するには、次の手順を実行します。  
  
1. 右クリックして**参照**プロジェクト、およびクリックで**サービス参照の追加**します。  
  
2. **サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**します。  
  
3. **サービス参照設定**ダイアログ ボックスで、をクリックして**Web 参照の追加**します。  
  
4. URL を入力し、クリックして**移動**します。  
  
5. クリックして**参照の追加**Web 参照を追加します。  
  
   > [!TIP]
   >  BizTalk プロジェクトに Web 参照を追加した後、 **Web 参照の追加**メニュー オプションは、参照、Web 参照とプロジェクトのノードで使用できます。  
  
   サービスおよび Web 参照を追加する方法の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=131577](http://go.microsoft.com/fwlink/?LinkId=131577)します。  
  
## <a name="msbuild-integration"></a>MSBUILD の統合  
 Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージド プロジェクトに関するビルド情報を保存します。 詳細については、次を参照してください。 [MSBUILD と Visual Studio の統合](../core/msbuild-integration-with-visual-studio.md)します。  
  
## <a name="team-foundation-server-integration"></a>Team Foundation Server の統合  
 BizTalk プロジェクトのソース制御システムとして Team Foundation Server を使用できます。 チェックインやチェックアウトなどの操作を [ソリューション エクスプローラー] ウィンドウ自体から実行できます。  
  
## <a name="support-for-unit-testing"></a>単体テストのサポート  
 この機能を使用すると、スキーマ、マップ、およびパイプラインの単体テストを実行できます。 詳細については、次を参照してください。 [BizTalk Server プロジェクトでの Unit Testing](../core/unit-testing-with-biztalk-server-projects.md)します。  
  
## <a name="debug-map-feature"></a>マップ機能のデバッグ  
 **マップ機能をデバッグ**します。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のインライン XSLT デバッガーを使用して、マップ (XSLT) をデバッグできます。 詳細については、次を参照してください。[マップのデバッグ方法](../core/how-to-debug-maps.md)します。  
  
## <a name="migrating-biztalk-server-projects"></a>BizTalk Server プロジェクトの移行  
 Visual Studio プロジェクトが以前のバージョンの用に開発された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Visual Studio 変換ウィザードを使用して、BizTalk Server 環境に移行できます。 詳細については、次を参照してください。 [BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)します。  
  
## <a name="release-and-debug-build-types"></a>リリース ビルドとデバッグ ビルドの種類  
 BizTalk プロジェクトに 2 つのビルドの種類があるようになりました:**リリース**と**デバッグ**、後継**開発**と**展開**の前バージョン。 ただし、引き続きを参照してください、**開発**と**展開**から移行されるプロジェクトの構成[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]します。  
  
## <a name="embedding-tracking-and-debugging-information"></a>追跡情報とデバッグ情報の埋め込み  
 **追跡情報の埋め込み**と**デバッグ情報の生成**が出力構成プロパティに置き換え、 **TRACE 定数の定義**と**DEBUG 定数の定義**ビルド オプション、**ビルド**プロジェクト デザイナーのタブ。 **BPEL 準拠コードの生成**構成プロパティが置き換え**BPEL 準拠コードの生成**プロジェクトのプロパティ ウィンドウでプロパティ。  
  
> [!IMPORTANT]
>  Visual Studio 変換ウィザードでは、これらの設定が新しい環境に自動的に移行されます。  
  
## <a name="user-access-control"></a>ユーザー アクセス制御  
 Visual Studio では、管理者特権で Visual Studio を実行しない限り、ユーザー アクセス制御 (UAC) 機能が有効になったコンピューター上に BizTalk プロジェクトを展開できません。 管理者特権で Visual Studio を実行する をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Visual Studio**、右クリックして**Microsoft Visual Studio\<バージョン\>**、 をクリックし、**管理者として実行**します。  
  
## <a name="c-files-in-a-biztalk-project"></a>BizTalk プロジェクトの C# ファイル  
 BizTalk Server を使用すると、パッケージングを柔軟に行うのための BizTalk アイテムとヘルパー クラスを組み合わせることができます。  ただし、使用すると、新しい c# ファイルを追加することはできません、**新しい項目の追加**または**新しいクラスの追加**メニュー オプション。  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a>GenerateCSFiles レジストリ キーの廃止  
 **GenerateCSFiles**レジストリ キーは廃止されました。 生成されたすべての .cs ファイルは、[ソリューション エクスプローラー] ウィンドウに表示されます。 をクリックする必要があります **[すべてのファイル**ツール バー アイテムのソリューション エクスプ ローラー] ウィンドウで、一部の BizTalk アイテムに関連付けられた .cs ファイルを参照してください。