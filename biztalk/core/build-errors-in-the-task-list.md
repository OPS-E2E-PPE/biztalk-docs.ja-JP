---
title: タスク一覧のビルド エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, errors
- errors, building
ms.assetid: 05b36511-3031-4e13-ac2f-bfdbec0f48cb
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc22550629d8ae66652e0afe1da61b1443dc580
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357778"
---
# <a name="build-errors-in-the-task-list"></a>タスク一覧のビルド エラー
プロジェクト、またはソリューションをビルドするときに、個々 のエラーと警告がタスク一覧に表示されます、[出力] ウィンドウで、結果が表示されます。  
  
 タスク一覧には、エラーと警告が表示されます。 エラーをダブルクリックして、フォーカスを正しく構成されていないオブジェクトに適用されます。  
  
> [!NOTE]
>  ビルドすると、コンパイラは Xpath を検証しません。 有効な XPath 構文を使用して、注意してください。  
  
## <a name="insufficient-configuration-action"></a>不十分な構成アクション  
 ![](../core/media/ebiz-orch-insufficconfig.gif "ebiz_orch_insufficconfig")  
  
> [!CAUTION]
>  オーケストレーション デザイナーを提供すると、不十分な構成の警告をこのような警告がない場合、オーケストレーションが正しくコンパイルされるという保証はありません。  
  
## <a name="compiler-asks-if-you-are-missing-an-assembly-reference"></a>コンパイラがアセンブリ参照が欠落しているかどうかを求める  
  
### <a name="problem"></a>問題  
 "をアセンブリ参照が存在しますか?"という質問で終了するエラー メッセージを表示するオーケストレーションをコンパイルするときに 2 つの一般的なメッセージは。  
  
-   型または名前空間の名前 'X' は名前空間 'Y' に存在しません (する、アセンブリ参照が存在しますか?)  
  
-   識別子 'X' が 'Y'; に存在しません。アセンブリ参照が見当たりませんか。  
  
### <a name="cause"></a>原因  
 このエラーの原因は次のいずれかの可能性があります。  
  
-   プロジェクトは、1 つまたは複数の必要なアセンブリを参照していません。  
  
-   プロジェクトには、マップまたはその他のプロジェクトと同じ名前を持つオブジェクトの種類が存在します。  
  
-   プロジェクトで XML スキーマ定義言語 (XSD) を使用-プロセス PIP (Partner Interface) のスキーマに基づいており、System という名前のサブフォルダーに XSD スキーマを含みます。  
  
-   プロジェクトには、名前空間を持つ現在のプロジェクトの名前空間のサブセットであるグローバル プロパティが使用しています。 たとえば、プロジェクト"Accounts.FILE"に含まれるオーケストレーション内のグローバル プロパティ名前空間"File.ReceivedFileName"を使用します。  
  
### <a name="resolution"></a>解決策  
 問題の原因によっては、解決策があります、次のいずれか。  
  
-   不足しているへの参照を追加するアセンブリのプロジェクトが必要です。  
  
-   プロジェクト名以外に、マップまたはその他のオブジェクトの名前を変更します。 これは、オブジェクトのプロパティ ページで通常行うことができます (たとえば、Name プロパティを含むプロパティ [マップ] ページ)。  
  
-   Visual Studio 内のスキーマの名前空間を変更します。 Visual Studio を使用してこれを行うに**すべてのファイル**で、**プロジェクト** メニューの 順に展開し、**システム**ソリューション エクスプ ローラーでノード。 システム フォルダーおよびすべてのサブフォルダーでは、各ファイルをクリックし、[プロパティ] ウィンドウで名前空間エントリを変更に出現する**システム**なります _**システム**します。 たとえば、変更、 **MyProject.System.SubFolder**名前空間を**MyProject._System.Subfolder**名前空間。 サポート技術情報の記事を参照してください、この問題の詳細については[916649](http://support.microsoft.com/?kbid=916649)します。  
  
-   競合するグローバル プロパティ名前空間をプロジェクトから削除します。  
  
## <a name="you-receive-a-message-has-not-been-initialized-in-construct-statement-error-when-building-your-project"></a>プロジェクトのビルド時に「メッセージが初期化されていません construct ステートメントで」エラーが発生します。  
  
### <a name="problem"></a>問題  
 エラーが発生する、BizTalk アプリケーションをコンパイルするときに「メッセージが初期化されていません construct ステートメントで」。  
  
### <a name="cause"></a>原因  
 メッセージを構築する場合は、すべてのメッセージ変数を指定します。 メッセージまたはメッセージの部分に割り当てを行います。 別の特定のメッセージの割り当ての一部が含まれているかどうかは**メッセージの構築**図形、初期化のエラー メッセージが表示される可能性があります。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、同じ特定のメッセージの割り当てのすべての部分を含めることを確認します**メッセージの構築**図形。 関連するサポートの問題点、サポート技術情報の記事を参照してくださいについて[870606](http://support.microsoft.com/?kbid=870606)します。  
  
 内のメッセージを作成して、この問題を解決することができますも、**構築**図形内のイメージのインスタンスを使用する前に、**式**図形。 たとえば、次のコード エラーが発生に配置されている場合、**式**図形。  
  
```  
XMLDOM = new System.Xml.XmlDocument();  
POAckMsg = XMLDOM;  
```  
  
 を解決するには、内に XMLDOM のインスタンスを作成、**構築**図形し、ダウン ストリームの割り当てを行って**式**図形。  
  
## <a name="you-receive-a-use-of-unconstructed-message-error-when-building-your-project"></a>プロジェクトのビルド時に「未構築のメッセージの使用」エラーが発生します。  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをコンパイルするときにエラーが発生した"未構築のメッセージの使用 '\<メッセージ\>'"です。  
  
### <a name="cause"></a>原因  
 未構築のメッセージを使用すると、このエラーが発生した、**送信**図形。  
  
### <a name="resolution"></a>解決策  
 この問題を解決するには、追加、**メッセージの構築**オーケストレーションへの図形。 含める、**メッセージの構築**図形の前に、**送信**Web サービスにバインドされている図形。  
  
 このエラーとサポート技術情報の記事を参照してください、Web サービスの詳細については[921043](http://support.microsoft.com/?kbid=921043)します。  
  
## <a name="setting-a-transaction-level-for-a-scope-results-in-an-error"></a>エラーの結果を絞り込む、トランザクション レベルを設定します。  
  
### <a name="problem"></a>問題  
 スコープの入力、トランザクションを構成または他のエンティティでは、オーケストレーションでのトランザクションのサポート、エラーが発生した後に「非トランザクション オーケストレーションを含めることはできません他のトランザクション」。  
  
### <a name="cause"></a>原因  
 このエラーと発生しますスコープ (またはその他のエンティティ) のトランザクションの種類を構成しようとすると「アトミック」または「実行時間の長い」するためのオーケストレーションで、オーケストレーション自体がある"None"のトランザクションの種類。  
  
### <a name="resolution"></a>解決策  
 オーケストレーションと構成のオブジェクトのトランザクションの種類の設定に互換性があることを確認します。  
  
## <a name="project-build-results-in-the-error-you-must-specify-at-least-one-already-initialized-correlation-set-for-a-non-activation-receive-that-is-on-a-non-selfcorrelating-port"></a>プロジェクト ビルド エラーが発生"する必要があります 1 つ以上指定初期化済みの関連付けが非アクティブ化の設定が表示される非自己関連付けを行わないポート上にある"  
  
### <a name="problem"></a>問題  
 BizTalk プロジェクトをコンパイルするときに、"する必要があります 1 つ以上指定初期化済みの関連付けが非アクティブ化の設定が表示される非自己関連付けを行わないポート上にある"エラーが表示されます。  
  
### <a name="cause"></a>原因  
 アクティブ化するオーケストレーションが存在しない場合、このエラーが発生する可能性が**受信**図形 (Activate = true)、またはアクティブ化がありません**受信**図形し、は別のオーケストレーションによって直接呼び出されません。  
  
### <a name="resolution"></a>解決策  
 オーケストレーションが別のオーケストレーションによって呼び出されない場合のいずれかを構成する必要があります、**受信**をアクティブ化された受信図形。 構成の詳細については、**受信**図形、相関関係へのリンクなどを参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)します。  
  
## <a name="you-receive-the-error-assembly-generation-failed----referenced-assembly-assembly-does-not-have-a-strong-name-when-building-your-solution"></a>エラーが発生した"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ\>' 厳密な名前が"ソリューションを構築するときに  
  
### <a name="problem"></a>問題  
 エラーが発生した"アセンブリの生成に失敗しました--参照されたアセンブリ '\<アセンブリ\>' 厳密な名前ではありません"がオーケストレーション ソリューションを構築した場合にします。  
  
### <a name="cause"></a>原因  
 この問題は、符号なしの参照先アセンブリの型は、オーケストレーション内で使用する場合に発生します。  
  
### <a name="resolution"></a>解決策  
 参照アセンブリに厳密な名前を適用します。 カスタム アセンブリが再コンパイルすることができますがの場合は、厳密な名前ツールを使用して、.snk (キー) ファイルを作成し、プロジェクトのアセンブリのプロパティのキー ファイルを参照します。 アセンブリを厳密な名前付けの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)します。  
  
## <a name="the-error-failed-to-add-resources-change-requests-failed-for-some-resources-occurs-when-deploying-an-orchestration"></a>"リソースの追加に失敗しましたエラー。 オーケストレーションを展開するときに発生する変更要求の一部のリソースに失敗しました"  
  
### <a name="problem"></a>問題  
 オーケストレーションを展開するには、次のようなエラーが表示され、オーケストレーションの展開は失敗します。  
  
```  
Failed to add resource(s). Change requests failed for some resources. BizTalkAssemblyResourceManager failed to complete end type change request. Object reference not set to an instance of an object.  
```  
  
### <a name="cause"></a>原因  
 このエラーは、オーケストレーションに使用する任意のオブジェクトが含まれている場合に発生する可能性がC#キーワード。  
  
### <a name="resolution"></a>解決策  
 削除C#オーケストレーションからのキーワード。 一覧についてはC#キーワードを参照してください[ http://go.microsoft.com/fwlink/?LinkId=74346](http://go.microsoft.com/fwlink/?LinkId=74346)します。  
  
## <a name="you-receive-an-invalid-property-value-error-when-compiling-your-orchestration"></a>オーケストレーションをコンパイルするときに、「無効なプロパティの値」エラーを受信します。  
  
### <a name="problem"></a>問題  
 「無効なプロパティの値」エラー ダイアログが表示されたら、オーケストレーションを構築するときにします。  
  
### <a name="cause"></a>原因  
 1 つ以上のソリューション内のオブジェクトは、別のオブジェクトと同じ名前を持ちます。 たとえば、メッセージ名は、ポート名と同じ。  
  
### <a name="resolution"></a>解決策  
 ソリューション内のすべてのオブジェクトに一意の名前があることを確認します。 名前付け規則に従うことで、このエラーのリスクを最小限に抑えることができます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションを構築する方法](../core/how-to-build-orchestrations.md)