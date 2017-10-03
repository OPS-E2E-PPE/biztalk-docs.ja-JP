---
title: "タスク一覧内のビルド エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bfd5b9f7b974b00d63831484ecbaa44e2568fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="build-errors-in-the-task-list"></a>タスク一覧内のビルド エラー
プロジェクト (ソリューション) をビルドすると、個別のエラーおよび警告がタスク一覧に表示され、結果は出力ウィンドウに表示されます。  
  
 エラーおよび警告は、タスク一覧に表示されます。 エラーをダブルクリックすると、正しく構成されていないオブジェクトにフォーカスが移動します。  
  
> [!NOTE]
>  ビルドを行うとき、コンパイラは XPath を検証しないため、 有効な XPath 構文を使用してください。  
  
## <a name="insufficient-configuration-action"></a>不十分な構成の操作  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  オーケストレーション デザイナーでは状況に応じて不十分な構成の警告が発生しますが、この警告が発生しないからといってオーケストレーションが正しくコンパイルされるという保証はありません。  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a>コンパイラによるアセンブリ参照の確認  
  
### <a name="problem"></a>問題  
 オーケストレーションをコンパイルすると、"アセンブリ参照があるか確認してください" で終わるエラー メッセージが表示されます。 以下の 2 つが一般的なメッセージです。  
  
-   型または名前空間名 'X' は名前空間 'Y' に存在しません。アセンブリ参照が不足しています。  
  
-   識別子 'X' は 'Y' に存在しません。アセンブリ参照があるか確認してください。  
  
### <a name="cause"></a>原因  
 次のいずれかが原因で、このエラーが発生します。  
  
-   プロジェクトは 1 つ以上の必要なアセンブリを参照していません。  
  
-   プロジェクトに、プロジェクトと同じ名前のマップまたはその他のオブジェクトの種類が存在します。  
  
-   プロジェクトは XSD (XML スキーマ定義) 言語ベースの PIP (Partner Interface Process) スキーマを使用し、System という名前のサブフォルダーに XSD スキーマが含まれています。  
  
-   プロジェクトは、名前空間が現在のプロジェクトの名前空間のサブセットになっているグローバル プロパティを使用しています。 たとえば、プロジェクト "Accounts.FILE" に含まれているオーケストレーションでグローバル プロパティ名前空間 "File.ReceivedFileName" を使用しています。  
  
### <a name="resolution"></a>解決策  
 問題の原因に応じて、次の解決策があります。  
  
-   欠落しているアセンブリへの参照をプロジェクトに追加します。  
  
-   マップまたは他のオブジェクトの名前を、プロジェクト名とは異なる名前に変更します。 これは通常、オブジェクトのプロパティ ページで実行できます (たとえば、マップのプロパティ ページには、"名前" プロパティが含まれています)。  
  
-   Visual Studio でスキーマの名前空間を変更します。 Visual Studio を使用してこれには、をクリックして**すべてのファイル**上、**プロジェクト** メニューの 順に展開し、**システム**ソリューション エクスプ ローラー内のノードです。 各ファイル システム フォルダーとサブフォルダーをクリックし、[プロパティ] ウィンドウで名前空間のエントリをする変更の発生**システム**_ になります**システム**です。 たとえば、変更、 **MyProject.System.SubFolder**名前空間を**MyProject._System.Subfolder**名前空間。 サポート技術情報の記事を参照して、この問題の詳細については[916649](http://support.microsoft.com/?kbid=916649)です。  
  
-   プロジェクトから、競合するグローバル プロパティ名前空間を削除します。  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a>プロジェクトのビルド時に発生する "メッセージは construct ステートメントで初期化されていません" エラー  
  
### <a name="problem"></a>問題  
 エラーが発生する、BizTalk アプリケーションをコンパイルするときに「メッセージが初期化されていません construct ステートメントで」です。  
  
### <a name="cause"></a>原因  
 メッセージを作成するときに、すべてのメッセージ変数を指定します。 メッセージまたはメッセージの部分に割り当てを行います。 別の特定のメッセージの割り当ての一部が含まれているかどうかは**メッセージの構築**図形、初期化エラー メッセージが表示される可能性があります。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、同じで、特定のメッセージの割り当てのすべての部分を含めることを確認します**メッセージの構築**図形です。 サポート技術情報の記事を参照して関連するサポートの問題点[870606](http://support.microsoft.com/?kbid=870606)です。  
  
 メッセージを作成することで、この問題を解決することができますも、**構築**図形で、そのインスタンスを使用する前に、**式**図形です。 たとえば、次のコード エラーが発生に配置されている場合、**式**図形。  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 を解決するには、内に XMLDOM のインスタンスを作成、**構築**図形、および、ダウン ストリームの割り当てを行う**式**図形です。  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a>プロジェクトのビルド時に発生する "未構築のメッセージが使用されました" エラー  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをコンパイルするときに、エラー"未構築のメッセージの使用 '\<メッセージ >'"です。  
  
### <a name="cause"></a>原因  
 未構築のメッセージを使用する場合、このエラーが発生した、**送信**図形です。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、追加、**メッセージの構築**オーケストレーションへの図形です。 含める、**メッセージの構築**図形の前に、**送信**Web サービスにバインドされている図形です。  
  
 詳細については、このエラーと Web サービス、サポート技術情報の記事を参照してください[921043](http://support.microsoft.com/?kbid=921043)です。  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a>エラーで、その結果、スコープのトランザクション レベルの設定  
  
### <a name="problem"></a>問題  
 オーケストレーション内のスコープまたはトランザクションをサポートするその他のエンティティのトランザクションの種類を構成した後に、"トランザクションでないオーケストレーションに他のトランザクションを含めることはできません" というエラーが表示されます。  
  
### <a name="cause"></a>原因  
 このエラーは、オーケストレーション自体のトランザクションの種類が "なし" である場合に、オーケストレーション内のスコープ (またはその他のエンティティ) のトランザクションの種類を "アトミック" または "長時間トランザクション" に構成しようとすると発生します。  
  
### <a name="resolution"></a>解決策  
 オーケストレーションと構成要素であるオブジェクトのトランザクションの種類の設定が互換することを確認します。  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a>プロジェクトのビルドによって発生する "自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" エラー  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをコンパイルすると、"自己関連付けを行わないポート上での非アクティベーション受信に対して、既に初期化されている関連付けセットを少なくとも 1 つ指定する必要があります" というエラーが表示されます。  
  
### <a name="cause"></a>原因  
 アクティブ化、オーケストレーションが存在しない場合、このエラーが発生する可能性が**受信**図形 (Activate = true) のアクティブ化がないか**受信**図形し、は別のオーケストレーションによって直接呼び出されません。  
  
### <a name="resolution"></a>解決策  
 オーケストレーションが別のオーケストレーションによって呼び出されない場合のいずれかを構成する必要があります、**受信**アクティブ化受信である図形です。 構成の詳細については、**受信**関連付けへのリンクを含む図形を参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)です。  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a>エラーが発生する"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ >' は厳密な名前がありません"ソリューションをビルドする場合  
  
### <a name="problem"></a>問題  
 エラーが発生する"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ >' は厳密な名前がありません"ときにオーケストレーションを持つソリューションを構築します。  
  
### <a name="cause"></a>原因  
 この問題は、署名されていない参照アセンブリの型がオーケストレーション内で使用されている場合に発生します。  
  
### <a name="resolution"></a>解決策  
 参照アセンブリに厳密な名前を適用します。 このアセンブリが再コンパイル可能なカスタム アセンブリである場合は、厳密名ツールを使用して .snk (キー) ファイルを作成してから、プロジェクトのアセンブリ プロパティ内でそのキー ファイルを参照します。 アセンブリを厳密な名前付けの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)です。  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a>オーケストレーションの展開時に発生する "リソースの追加に失敗しました。 一部のリソースに対する変更要求に失敗しました。" エラー  
  
### <a name="problem"></a>問題  
 オーケストレーションを展開するときに、次のようなエラーが表示され、オーケストレーションの展開は失敗します。  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a>原因  
 このエラーは、オーケストレーションに、C# キーワードを使用するオブジェクトが含まれている場合に発生する可能性があります。  
  
### <a name="resolution"></a>解決策  
 オーケストレーションから C# キーワードをすべて削除します。 C# のキーワードの一覧は、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)です。  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a>オーケストレーションのコンパイル時に発生する "無効なプロパティ値" エラー  
  
### <a name="problem"></a>問題  
 オーケストレーションをビルドしているときに、"無効なプロパティ値" エラー ダイアログが表示されます。  
  
### <a name="cause"></a>原因  
 ソリューション内の 1 つ以上のオブジェクトが別のプロジェクトと同じ名前になっています。 たとえば、メッセージ名がポート名と同じになっています。  
  
### <a name="resolution"></a>解決策  
 ソリューション内のすべてのオブジェクトの名前が一意であることを確認します。 名前付け規則に従うことで、このエラーの発生を最小限に抑えることができます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションを構築する方法](../core/how-to-build-orchestrations.md)