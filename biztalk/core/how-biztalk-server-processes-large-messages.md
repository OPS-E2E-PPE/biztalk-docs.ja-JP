---
title: BizTalk Server がサイズの大きいメッセージを処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62c070be-dff5-4349-9e36-dd3a7caf1752
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9d2d31163dcb49861b1cdb6331579502960b6e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387490"
---
# <a name="how-biztalk-server-processes-large-messages"></a>BizTalk Server がサイズの大きいメッセージを処理する方法
## <a name="what-is-a-large-message"></a>サイズの大きいメッセージは何ですか。  
 残念ながら、この質問に対する回答のものではなく、特定のメッセージ サイズに直接結び付けられていない、microsoft の特定のボトルネックによって異なります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 サイズの大きいメッセージに関連する問題は、次のカテゴリに分類できます。  
  
-   **メモリ不足エラー**特定種類のマッピング、検証、およびプロパティの昇格などのメッセージの処理がメモリにメッセージ全体を読み込みます。 メモリ内のメッセージのサイズが使用可能なリソースを超えている場合は、メモリ エラーが発生します。 このカテゴリに分類されるメッセージのサイズのしきい値は、メモリに読み込まれていないメッセージのサイズのしきい値よりはるかに劣ります。 たとえば、10 MB のフラット ファイルを XML に解析され、そのマップが 10 倍で拡張することがありますまたは解析または月を実際にマップされているは 100 MB の XML ドキュメントは、100 MB を超えるメモリを使用する詳細はありませんのみストリーミングされる際に 1 MB のメモリを消費します。メッセージ ボックス データベースです。  
  
-   **パフォーマンスの問題をメモリに読み込まれていないメッセージ**メモリに読み込まれる必要がないメッセージは、.NET XmlReader インターフェイスを使用して、メッセージ ボックス データベースにストリーム送信されます。 メモリに読み込む必要があるメッセージのサイズの制限が適用されていないときに BizTalk Server でのメッセージ ボックス データベースにストリーム配信されるメッセージの処理方法に影響を与えるいくつかの重要な要因があります。  
  
## <a name="factors-that-affect-the-processing-of-large-messages"></a>サイズの大きいメッセージの処理に影響する要因  
 元のメッセージ サイズ、メッセージの形式とすべてのメッセージ処理の種類は、BizTalk Server がサイズの大きいメッセージを処理する方法に影響します。  
  
- **元のメッセージ サイズ**BizTalk Server で受信メッセージのサイズはの大きさ、メッセージが BizTalk Server によって処理されるときに、最も明確に示します。 メッセージの元のサイズは、メッセージ全体が、メッセージをメッセージ ボックス データベースにストリーミングされている場合よりもメモリに読み込まれている場合、パフォーマンスに大きな影響が。  
  
- **メッセージ形式**で 2 つの主な形式のいずれかの BizTalk Server にメッセージを受信します。XML ファイルまたはフラット ファイル。  
  
  -   **XML ファイル**BizTalk Server でパススルー ルーティング以外のメッセージに対する処理を実行するためには、メッセージは、XML ファイル形式である必要があります。 処理するファイルは、ほとんどの場合、元のサイズが保存されますし、XML 形式で受信されます。 場合、  
  
  -   **フラット ファイル**フラット ファイルは、BizTalk Server でパススルー ルーティング以外の処理を行う前に、XML 形式に解析する必要があります。 XML ファイルでフラット ファイルを解析すると、ファイルのサイズが非常に大きくなる可能性があります。 フラット ファイルには、データに関する説明情報を持つ XML タグが含まれません。 一方、XML ファイルは、説明的な XML タグにすべてのデータを格納します。 一部のシナリオで解析サイズを増やし、フラット ファイルのファイルの XML タグに 10 個以上、に応じてどの程度わかりやすいデータが含まれているの倍数で。  
  
  -   **フラット ファイル ドキュメントの XML ドキュメントの単一の CDATA セクション ノードでラップ**この種類のドキュメントは XML とフラット ファイルの両方の組み合わせと BizTalk Server を使用して、ラップされたフラット ファイル ドキュメント全体を前に、メモリに読み込む必要がありますので、問題が発生することができますこれを処理します。  
  
- **メッセージ処理の種類**BizTalk Server では、2 つの種類のメッセージの処理。ルーティングのみとマッピングを選択します。 されるメッセージ処理の種類に関連付けられているパフォーマンス変数には、メッセージのサイズと、メッセージをメモリに読み込まれるかどうかを実行します。  
  
  - **ルーティングのみ**場合の BizTalk Server は、昇格させたメッセージ プロパティに基づいてメッセージをルーティングのみ使用し、メッセージは、.NET XmlReader インターフェイスを使用してメッセージ ボックス データベースにストリーミング メッセージ部分が個別にはできませんメモリに読み込まれます。 このシナリオでメモリ不足エラーが問題とならないと、主要な考慮事項は、メッセージ ボックス データベースに非常に大きいメッセージ (100 MB を超える) の書き込みに必要な時間。 開発チームの処理をテストして正常に BizTalk Server は、ルーティングのみを実行するときに、最大 1 GB のサイズをメッセージです。  
  
     このシナリオでパフォーマンスを決定する主な要因は、**サイズの大きいメッセージのフラグメント サイズ**データベースにデータを分割するために使用します。 **サイズの大きいメッセージのフラグメント サイズ**で構成可能なオプションは、 **BizTalk グループのプロパティ**構成 ページで 102,400 バイト (100 KB) の既定値。 この値を増やすと、メッセージ ボックス データベースにメッセージをストリーミングするために必要なラウンド トリップの回数が減少します。  
  
  - **マッピング**メモリを消費する操作は、マップでドキュメントを変換します。 BizTalk Server が、.Net にメッセージを渡すマップでドキュメントが変換されるときに XSLCompileTransform クラスは、XSL スタイル シートを読み込みます。 Load メソッドが正常に完了した後、変換メソッドが複数のスレッドから同時に呼び出すことができます。 [XslCompiledTransform クラス](http://go.microsoft.com/fwlink/p/?LinkID=282683)XSLCompiledTransform クラスについて詳しく説明します。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 変換中にメモリにドキュメントを読み込むための構成可能なメッセージ サイズのしきい値を実装することで、サイズの大きいドキュメントのメモリ管理を大幅に向上します。 このしきい値よりも小さいサイズのすべてのメッセージがメモリ内で処理されます。このしきい値を超えるサイズのすべてのメッセージは、メモリ要件を軽減するファイル システムにバッファリングされます。 既定のメッセージ サイズのしきい値は、1 MB です。  
  
## <a name="guidelines-for-processing-large-messages"></a>サイズの大きいメッセージを処理するためのガイドライン  
 BizTalk Server でサイズの大きいメッセージを処理するときに、パフォーマンスを向上させるためにこれらのガイドラインに従います。  
  
1. これを超えるバッファリングされるドキュメント、ファイル システムにマッピング中に、メッセージ サイズのしきい値を調整します。 という名前の DWORD 値を作成、サイズのしきい値を変更する**TransformThreshold** BizTalk Server レジストリの次の場所。  
  
   ```  
   HKLM\Software\Microsoft\BizTalk Server\3.0\Administration\TransformThreshold  
   ```  
  
    この値を作成した後に新しいしきい値を設定するバイト数を 10 進値を入力します。 たとえば、2097152 (1 MB の既定値) から 2 MB に、メッセージ サイズのしきい値を上げるための 10 進値を入力します。 大量のスループットを向上させるために使用可能なメモリを備えたシステムでは、この値を増やします。 ドキュメントをディスクにバッファリングすると、全体的なスループットのコストでメモリを節約できます。  
  
   > [!NOTE]
   >  既定では、マッピング中に、ファイル システムにバッファリングされるドキュメントに書かれて、 *%temp%* BizTalk Server コンピューターのディレクトリ。 設定を変更、 *%temp%* マッピング中に、ファイル システムに大量のメッセージをバッファリングする場合は、パフォーマンスを向上させるためにシステム以外のディスクに環境変数。  
  
2. オーケストレーションでマップの使用を最小限に抑えます。  
  
   -   抽出または使用するプロパティを設定するマップを使用している場合、オーケストレーションでビジネス ロジックは識別フィールドを使用して、または代わりに、昇格させたプロパティ。 抽出またはマップで値を設定するときは、メモリにドキュメントが読み込まれます。 識別フィールドまたは昇格させたプロパティを使用して、オーケストレーション エンジンがメッセージ コンテキストにアクセスして、ドキュメントをメモリに読み込まれません。  
  
   -   いくつかのフィールドを 1 つのフィールドに集計を識別フィールドを使用して、マップを使用して結果セットを蓄積するオーケストレーション変数のプロパティを昇格するか。  
  
   -   複数の入力が変換図形でオーケストレーションを構成しないでください。 変換図形の複数の入力を含むオーケストレーションは、マッピング中にファイル システムにストリーム配信されません。 この制限には、ドキュメントのサイズが指定した TransformThreshold レジストリ値を超えた場合に、メモリに読み込むにマップされているドキュメントの全体が発生します。 オーケストレーション受け入れない変換図形の 1 つの入力よりも多くするため、この問題を回避するには、適用するには 1 つは受信ポートのレベルでは変換します。  
  
3. 調整、**サイズの大きいメッセージのフラグメント サイズ**プロパティで公開されている、 **BizTalk グループのプロパティ**構成 ページ。  
  
    受信したメッセージのメモリ内サイズが指定されたバイト数を超えた場合**サイズの大きいメッセージのフラグメント サイズ**メッセージは、指定されたサイズのフラグメントに分割し、フラグメントは、メッセージ ボックス データベースに書き込まれます、。次のように、Microsoft 分散トランザクション コーディネーター (MSDTC) トランザクションのコンテキスト:  
  
   1.  受信メッセージは、既存の MSDTC トランザクションのコンテキストで公開されているが場合、は、メッセージ ボックスに、メッセージのフラグメントを書き込むときにし、このトランザクションは使用されます。 たとえば、受信メッセージは、既存のトランザクションは、メッセージの書き込み時に、使用は、トランザクションを要求するように構成されたトランザクション アダプターによって公開されている場合は、メッセージ ボックスにフラグメントします。  
  
   2.  受信メッセージが既存の MSDTC トランザクションのコンテキストで公開されていない場合は、メッセージのフラグメントを記述する、新しい MSDTC トランザクションが作成されます。  
  
   -   値を大きく**サイズの大きいメッセージのフラグメント サイズ**がサイズの大きいメッセージが断片化しているし、関連付けられた MSDTC トランザクションの作成の頻度を減らすの頻度を減らします。 MSDTC トランザクションを使いすぎるとパフォーマンスの観点で無駄が多いため、この操作を実行する必要があります。 この値を大きくすると使用できるメモリの量も増える可能性があるので注意してください。  
  
   -   場合は、トランザクションがタイムアウトになる、エラーが発生し、メッセージの書き込みに失敗すると、メッセージ ボックスにメッセージを記述する 60 分間の許容される MSDTC トランザクションの最大タイムアウトより長くかかるしはロールバックされます。 **サイズの大きいメッセージのフラグメント サイズ**値は非常に大きなメッセージを処理するときに、この問題を回避するために大ききます。 使用できるメモリの量に応じて、この値を最大値 1000000 バイトに設定する必要があります。  
  
   -   メッセージの各フラグメントは、メッセージ ボックス データベースに対して 1 つ以上の SQL Server データベース ロックを作成します。 ロックの数が数十万を超える場合は、"ロック"の範囲外のエラーを生成する SQL Server が起動することができます。 この問題が発生した場合の向上、**サイズの大きいメッセージのフラグメント サイズ**メッセージ ボックス データベースに対して行われた SQL Server データベース ロックの数を減らします。  
  
4. "ロック"の範囲外のエラーが発生した場合、64 ビット バージョンの SQL Server でメッセージ ボックス データベースを格納していることを検討してください。 使用可能なロックの数は、64 ビット バージョンの SQL Server で大幅に高くなっています。  
  
5. 調整、**サイズの大きいメッセージのしきい値**プロパティで公開されている、 **BizTalk グループのプロパティ**構成 ページ。  
  
    メッセージ バッチのメモリ内サイズが指定されたバイト数に達した場合、メッセージとしてバッチが処理は**サイズの大きいメッセージのしきい値**が処理されたメッセージのバッチの部分が前に、メッセージ ボックス データベースに書き込まれますメッセージ バッチの残りの部分が処理されます。 これは、MSDTC トランザクションのコンテキストで、次のように。  
  
   1. メッセージ バッチは、既存の MSDTC トランザクションのコンテキストで公開されているが場合、は、メッセージ バッチの処理部分をメッセージ ボックス データベースに書き込むときに、このトランザクションは使用されます。 受信メッセージ バッチはトランザクションし、既存のトランザクションを要求するように構成されたトランザクション アダプターによって公開されている場合の例は、メッセージ ボックスに、メッセージ バッチの処理部分を記述するときに使用されます。  
  
   2. メッセージ バッチが既存の MSDTC トランザクションのコンテキストで公開されていない場合、メッセージ ボックスに、メッセージ バッチの部分を記述する、新しい MSDTC トランザクションを作成する必要があります。 MSDTC トランザクションを使用して、特定のメッセージ バッチの各部分のすべてが正常に書き込まれるように、メッセージ ボックス データベースにします。  
  
      **サイズの大きいメッセージのしきい値**設定は、メッセージのバッチに直接適用できますが、メッセージ バッチは、1 つの値に設定することができます、**サイズの大きいメッセージのしきい値**設定解除することも直接個々 のメッセージに適用されます。 たとえば 1 つのメッセージのメッセージのバッチを超える場合、指定した**サイズの大きいメッセージのしきい値**パラメーター、**サイズの大きいメッセージのしきい値**バッチ内の 1 つのメッセージにのみ有効で適用されます。  
  
   -   **サイズの大きいメッセージのしきい値**パラメーターは、メッセージ ボックスにメッセージのバッチを割り当てるために使用される MSDTC トランザクションの作成を軽減するために調整する必要があります。 MSDTC トランザクションの過剰な使用はパフォーマンスの観点からコストの高いために、これを実行する必要があります。 最小値を決定する次の計算を使用して、**サイズの大きいメッセージのしきい値**設定は、MSDTC トランザクションを不必要に作成しないようにする必要があります。  
  
       ```  
       Batch Size * Average size (in bytes) of each message in the batch after being processed by the receive pipeline < Large message threshold  
       ```  
  
        メッセージ バッチのバイト単位の合計サイズが指定された値を超えない限り、**サイズの大きいメッセージのしきい値**メッセージ ボックスに、メッセージ バッチを分配するために BizTalk で、MSDTC トランザクションを開始する必要はありませんデータベース。