---
title: BizTalk Server 開発アイテムのソース管理システムの制御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce25b112-38c9-40c8-9a5f-a2855572aabb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce9483518275c57c7defb730aeeffc8a4139115
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991011"
---
# <a name="managing-biztalk-server-developer-artifacts-with-a-source-control-systems"></a>ソース管理システムを使用した BizTalk Server の開発アイテムの管理
BizTalk プロジェクトを予期しないシステム障害から保護することは、最優先事項として考える必要があります。 プロジェクト ファイルを保護する方法の 1 つは、Team Foundation Server ソース管理や Microsoft Visual SourceSafe のようなソース コード管理システムを使用することです。 ここでは、任意のソース管理システムで最適に動作するようプロジェクトを編成するための基本的な方法について説明し、Visual SourceSafe の具体的な使用方法を紹介します。  
  
## <a name="basic-organization-strategies"></a>基本的な編成方法  
 基本的な編成方法は、最終的に使用するソース管理システムの種類に関係なく採用できます。 この方法で編成した BizTalk プロジェクト ファイルの構造は、開発にもソース コード管理にも適したものです。  
  
### <a name="use-a-consistent-folder-structure-for-solutions-and-projects"></a>ソリューションとプロジェクトに一貫性のあるフォルダー構造を使用する  
 チーム環境で開発を行う場合、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューションとプロジェクトの保存にチーム全体で共通の構造を使用すると、管理が容易になります。 このことは特に、各 BizTalk プロジェクトにおいて、ビルド チーム、テスト チーム、および開発チームに必要なファイル (バインド ファイルなど) を生成および使用する場合に当てはまります。  
  
 フォルダー構造を標準化する時間をとらずに開発を始めることは簡単な場合もありますが、 後のソリューション開発でプロジェクトのリンクやテスト ハーネスに修正を加える必要が生じた場合、手間が増えることは避けられません。  
  
### <a name="keep-source-control-and-file-system-structures-identical"></a>ソース管理システムとファイル システムの構造を同じに維持する  
 複数の開発者が作業する環境に対し、管理を簡素化するには、ソース管理システム内のフォルダー構造をローカル ファイル システムの構造と同じに設定します。 こうすると、開発者は簡単に最新バージョンを入手して保存でき、チームの標準に従ったディスクの構造を維持できます。  
  
### <a name="define-and-use-a-common-root-folder"></a>共通のルート フォルダーを定義および使用する  
 すべてのプロジェクト コードと成果物は、1 つのフォルダー ルートで保持することをお勧めします。こうすると、同じルートをすべての開発者のコンピューターに作成できます。 すべての開発者が同じルートを使用すると、開発アイテムの管理と構成の一貫性を容易に維持できます。 たとえば、Visual SourceSafe 内に $/SysInteg2009 というルート フォルダーを作成すれば、すべての開発者がそれぞれのローカル ファイル システムに C:\SysInteg2009 というルート フォルダーを作成できます。  
  
### <a name="create-a-master-solution-that-will-hold-all-projects"></a>すべてのプロジェクトを保持するマスター ソリューションを作成する  
 マスター ソリューションは、通常メインのビルド ソリューションとして使用されます。 この方法は、複雑さの度合いが普通または高い BizTalk プロジェクトに対してお勧めです。  
  
### <a name="store-all-biztalk-projects-under-the-master-solution"></a>マスター ソリューションにすべての BizTalk プロジェクトを保存する  
 マスター ソリューション下で、関連するすべての BizTalk プロジェクトを編成すると便利です。 ソース管理システムの構造には、同じ階層を用意する必要があります。  
  
### <a name="divide-the-folder-structure-into-shared-and-process-specific-sections"></a>フォルダー構造を共有部分とプロセス固有の部分に分割する  
 ファイル構造を作成する場合、通常はフォルダー構造を分割し、共有エンティティとビジネス プロセス固有のエンティティとを切り離します。 共有エンティティは複数のプロジェクトに共通のエンティティで、ヘルパー クラスが含まれることもあります。  
  
 たとえば、次に挙げる最初の 3 つのフォルダーは共有エンティティによって編成されたもので、最後の 2 つのフォルダーはビジネス プロセスによって編成されたものです。  
  
 C:\SysInteg2009\\_Master_Solution\Shared\  
  
 C:\SysInteg2009\\_Master_Solution\Shared\EmailHelper  
  
 C:\SysInteg2009\\_Master_Solution\Shared\SharedSchema  
  
 C:\SysInteg2009\\_Master_Solution\AccountRequest\  
  
 C:\SysInteg2009\\_Master_Solution\AccountValidate\  
  
### <a name="separate-pipeline-projects-into-distinct-projects"></a>パイプライン プロジェクトを個別のプロジェクトに分割する  
 パイプライン コンポーネントの開発では通常、ソリューションの他の部分から独立したパイプラインの変更と再テストが必要になります。 このため、多くの場合は、パイプライン ソリューションを個別の BizTalk プロジェクトとして保持しておくと便利です。こうすると、ソリューションの残りの部分を再バインドする必要なく、個別のパイプライン アセンブリを削除および再展開できます。  
  
 さらに、一般的には、実際のパイプライン インターフェイスを実装するコードと、パイプライン処理ロジックを別々のプロジェクトに保存します。その際には、BizTalk プロジェクト (.btp ファイルを含む) から [!INCLUDE[btsCSharp](../includes/btscsharp-md.md)] または Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)] プロジェクトへの参照を含めます。  
  
### <a name="keep-deployment-and-test-scripts-with-their-projects"></a>展開スクリプトとテスト スクリプトをプロジェクトと共に保持する  
 ビルドと展開を行う統合プロセスを開発できるようにするには、ビルド スクリプトとインストール スクリプトを個別の開発者が作成する一方、これらのスクリプトをソリューション全体の再利用可能部分として表示する必要があります。 スクリプトを再利用可能なスクリプトとして記述した場合は、完全なソリューション パッケージの展開などの複数のタスクで、そのスクリプトを再利用できます。 たとえば、展開および展開解除のスクリプトで、DLL およびバインド ファイル フォルダーの場所のパスを示すパラメーターを受け取る場合は、コンパイルされた [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アセンブリが別の場所に存在するときにこれらのスクリプトを再利用できます。  
  
 この方法を使用すると、開発者は特定の処理のインストール スクリプトをフォルダーに追加すれば、すべての処理の完全な展開を実行するための 1 つの処理を簡単に記述できます。  
  
### <a name="use-unique-strong-name-keys-when-appropriate"></a>必要に応じて厳密な一意名のキーを使用する  
 通常、1 つの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューションで使用されるキー ファイルは 1 つです。 これは、ソリューションが 1 つのエンティティとして扱われ、管理される場合に当てはまります。 開発中のビジネス ソリューションが事実上 2 つ以上の異なる部分から構成されている場合は、2 つのキー ファイルを使用する必要があるかどうかを検討してください。 このシナリオで複数のキーを使用すると、各部分は個別のエンティティとして扱われ、異なるアップグレード パスの設定などに使用できます。  
  
 ヘルパー プロジェクトについても、同様のことを検討できます。 ヘルパー プロジェクトが現在個別のエンティティであるか、将来個別のエンティティとなる場合は、異なる厳密な名前のキーを使用してビルドする必要があります。  
  
### <a name="put-dependent-dlls-into-a-separate-folder"></a>依存 DLL を別のフォルダーに格納する  
 フォルダー構造を作成するときには、ファイル依存関係として参照される DLL 用に共通のフォルダーを作成して、これらを格納すると便利です。 すべての開発者が同じフォルダー構造を使用すれば、開発者間またはワークステーション間でソリューションを移動しても、ファイル参照は維持されます。  
  
### <a name="keep-test-messages-in-a-msgs-folder"></a>テスト メッセージを "Msgs" フォルダーに保存する  
 スキーマを開発しメッセージを使用する場合、XML スキーマとオーケストレーションの処理に対して多くの異なるサンプル メッセージをテストするには、通常相当な労力が必要です。  
  
 サンプル メッセージにはビジネス ソリューションに有用なデータが含まれているため、これらのメッセージは実際のソリューションにおいて重要な資産になります。 通常、同じメッセージ内にランダムな値やダミーの値があると、処理が失敗する原因となります。 このため、サンプル メッセージを扱うときにはソリューションのコードと同様の注意を払う必要があります。  
  
 メッセージ ファイルの管理に役立つ方法として、テスト メッセージを "msgs" という名前の特定フォルダーに保存する方法があります。 "生成されたインスタンス" と "サンプル メッセージ" (既存のシステムからのメッセージなど) の両方が存在する場合は、開発したスキーマと実際のデータを比較できるよう、サンプル メッセージを別に保存すると便利です。  
  
 統合プロジェクトでは一般的に複数バージョンのスキーマが存在し、したがって、メッセージ ファイルのバージョンも複数になります。 サンプル メッセージを区別するには、バージョン番号を使用してファイル名を付けます。  
  
### <a name="managing-other-files"></a>他のファイルの管理  
 ファイルの種類に応じて、1 つのフォルダーにまとめて保存できるファイルもあれば、他のファイルと共に共通フォルダーに保存できるファイルもあります。 ファイルの種類ごとに取り扱い方針を立て、その方針に一貫して従ってください。  
  
## <a name="working-with-biztalk-server-and-visual-sourcesafe"></a>BizTalk Server および Visual SourceSafe の操作  
 ここでは、Visual SourceSafe の操作に関する具体的な注意事項について説明します。たとえば、Unicode の取り扱い、ソース管理のための [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の使用、チェックインのタイミング、バージョン管理などに関する注意事項について説明します。  
  
### <a name="solution-character-sets"></a>ソリューションの文字セット  
 Visual SourceSafe には、Unicode ファイルの使用に関連する既知の制限事項があります。 BizTalk ソリューションを使用する場合、Visual SourceSafe で BizTalk Server の Unicode ファイルが破損しないように対策を講じる必要があります。  
  
##### <a name="to-enable-visual-sourcesafe-to-work-with-biztalk-server-unicode-files"></a>Visual SourceSafe で BizTalk Server の Unicode ファイルを使用できるようにするには  
  
1. Visual SourceSafe 8.0 Admin を起動します。  
  
2. 使用する SourceSafe データベースを選択します。  
  
3. **[ツール]** メニューの **[オプション]** をクリックします。  
  
4. をクリックして、**ファイルの種類**タブ。  
  
5. バイナリ ファイルの一覧の最後に、次のファイルの種類を追加します。 ファイルの種類はセミコロンで区切ってください。  
  
    \*.btm;\*.btp;\*.xsd;\*.odx  
  
6. **[OK]** をクリックします。  
  
   これで Visual SourceSafe では、BizTalk Server ファイルの確認や形式の変更が試行されないようになります。  
  
### <a name="use-visual-studio-for-source-control-operations"></a>ソース管理操作に Visual Studio を使用する  
 Visual SourceSafe でプロジェクトを作成および操作する場合は常に、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に統合されている Visual SourceSafe のサポート メニューを使用して行う必要があります。 Visual SourceSafe エクスプローラーは使用しないでください。  
  
### <a name="when-to-check-in-biztalk-server-projects"></a>BizTalk Server プロジェクトをチェックインするタイミング  
 Visual SourceSafe を使用する場合は、コードが機能テストに合格し、関連コードに影響なくビルドできると開発者が確信できてから、コードをチェックインしてください。 この基準を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に適用した場合、ガイドラインは次のようになります。  
  
- メッセージ スキーマのみを含む BizTalk プロジェクトは、さまざまなサンプル メッセージでのスキーマのテストが正常に完了してからチェックインする。  
  
- ビジネス プロセスを含む BizTalk プロジェクトは、適切な入出力メッセージと正しい送受信ポートを使用したソリューションのテストが正常に完了してからチェックインする。  
  
- ASP.NET Web サービス プロジェクトは、Web サービス コードの、開始システムに対するテストまたはテスト ハーネスを使用したテストが完了してからチェックインする。  
  
  この基準に従うと、Visual SourceSafe リポジトリでは常に、正常に作成されテストされたビルドが保持されます。 "ナイト ビルド" の方法に従う場合、この原則は重要です。  
  
### <a name="checking-in-intermediate-versions"></a>中間バージョンのチェックイン  
 ファイルをチェックインする別の方法として、"中間" バージョンをチェックインする方法があります。 この方法を使用する場合、中間バージョンは機能テストに合格しておらず、正式なビルドではないと考えることができます。 これはソース管理システム内に含まれるバージョンは常にビルド可能であるという一般原則に反するため、一般的に推奨される方法ではありませんが、 ただし一部のチームは、これにより開発者は、ソース管理システムを使用して、チェックインし、正式なビルドにチェックインするための条件を満たすなしのバージョンをロールバックするため、このアプローチを選択します。  
  
 中間バージョンをチェックインする方法を使用する場合は、ソース管理システムに "ビルド可能な" バージョンが含まれるという前提が破棄されます。 したがって、中間バージョンとビルド バージョンを区別する必要があります。 Visual SourceSafe を使用すると、自動またはプロセス ベースのさまざまな方法でこれを実現できます。 以下に例を示します。  
  
-   開発者は、"ビルド可能な" バージョンを Visual SourceSafe に追加したときにビルド管理者に通知するというプロセスに従う。  
  
-   開発者は、ビルドの準備が完了したテスト済みのバージョンを、Visual SourceSafe 内の "昇格領域" にチェックインし、 この昇格領域を、マスター ビルドに基づくソースとして使用する。  
  
-   Visual SourceSafe COM インターフェイスを使用したコードまたはスクリプトを記述し、活用する。 たとえば、特定のラベルを使用して、ビルドの準備が完了したコードを表すことができます。この場合、スクリプトではそのラベルが検索され、Visual SourceSafe の別の分岐にこのソースが "固定" されます。 この後、この分岐をマスター ビルドのソースとして使用します。  
  
### <a name="comparing-files"></a>ファイルの比較  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソース ファイルの 2 つのバージョン間の相違点は、Visual SourceSafe を使用して確認できます。 この操作は、マップやスキーマなどのアイテム、およびテスト メッセージやエクスポートされた構成ファイルなどの関連ファイルを使用して実行できます。  
  
> [!NOTE]
>  マップを比較する場合は、確認を行う前に編集する必要があります。編集しなかった場合、Visual SourceSafe は、そのマップと次のバージョンのマップとの相違点を検索する際にバイナリ比較を実行します。 これは、編集を行わない限り、マップ XML にはエンコード情報が追加されないためです。  
  
### <a name="version-controlling-non-biztalk-server-project-files"></a>BizTalk Server プロジェクト以外のファイルのバージョン管理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用される追加ファイルには、Visual SourceSafe で有効にバージョン管理および保存できるものがあります。 これらのファイルには次のものが含まれます。  
  
- バインド ファイル (開発およびテスト ファイル)  
  
- カスタム パイプライン アセンブリ  
  
- テスト データ (テスト メッセージなど)  
  
- テスト ハーネス (プロジェクトの有効期間中に変化する場合があります)  
  
- ビルド スクリプト、開発スクリプト、および開始と停止のスクリプト (開発チームとビルド チーム間での共有が必要なもの)  
  
  こうしたファイルが [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の特定の BizTalk プロジェクトに関連する場合は、BizTalk プロジェクト内に格納し、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の統合ソース管理機能を使用して管理することができます。  
  
##### <a name="to-include-a-file-or-folder-into-an-existing-visual-studio-project"></a>ファイルまたはフォルダーを既存の Visual Studio プロジェクトに格納するには  
  
1.  ソリューション エクスプ ローラーでクリックして**すべてのファイル**します。  
  
2.  ソリューションに含めるフォルダーまたはファイルを選択します。  
  
3.  フォルダーまたはファイルを右クリックし、**プロジェクトに含める**します。  
  
> [!NOTE]
>  ソース管理下にある [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトのアイテムを管理するときには、Visual SourceSafe エクスプローラーを使用しないでください。  
  
### <a name="checking-the-visual-sourcesafe-database"></a>Visual SourceSafe データベースのチェックイン  
 Visual SourceSafe データベースのサイズが大きい場合、使用頻度が高い場合、または多数の同時実行ユーザーがデータベースにアクセスする場合は、Visual SourceSafe メニューから [VSS DB の分析] コマンドを定期的に実行することをお勧めします。 この分析でエラーが検出された場合は、[VSS DB の分析および修復] コマンドを使用してエラーを修正できます。 これら 2 つのコマンドを使用する場合は、Visual SourceSafe データベースをロックする必要があります。したがってこの場合は、すべてのユーザーが Visual SourceSafe から切断する必要があります。