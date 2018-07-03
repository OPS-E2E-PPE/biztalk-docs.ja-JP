---
title: DynamicReceive サンプル (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fa7c934-7ec3-45ad-b226-c8c53934ecb1
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af89bac79614268f4648f688d8cabfc913ed2277
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974131"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a>DynamicReceive サンプル (BizTalk Server サンプル)
DynamicReceive サンプルは、MQSeries キューの URI が動的に指定される場合に MQSeries キューから [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージを受信する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルで指定された MQSeries キューを動的に作成する、 **queueManager**、**キュー**、および**server**変数。 これにより、動的なシナリオを受信し、取得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で指定したフィルター条件に基づいて動的に指定された MQSeries キューからメッセージを**MQMD_MsgId**と**MQMD_CorrelId**メッセージ プロパティ。  
  
## <a name="how-this-sample-was-designed-and-why"></a>このサンプルをデザインした方法とその理由  
 MQSeries アダプターは、オーケストレーション内のキューの URI アドレスを指定することで、MQSeries キューからメッセージを動的に受信できます。 この機能は、オーケストレーションの送信請求 - 応答の送信ポートを使用して実行されます。  
  
 動的にメッセージを受信するでは、次を指定します、**式**オーケストレーションの図形。  
  
1. 次のプロパティを設定の受信を有効にする動的、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ: **MQSeries.DynamicReceive** = `'Yes'`  
  
2. ポート URI を設定して、メッセージの取得元のアドレスを指定します。 必要に応じて、次の内容を指定できます。  
  
   -   使用して、メッセージを取得する前に、待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。  
  
   -   メッセージを受信するための一致条件を指定します。 一致条件のオプションは**メッセージ ID**、 **CorrelationID**、 **GroupID**、および**MessageSequenceNumber**します。 「プロパティ Related to BizTalk Server」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396)の詳細。  
  
   これらのプロパティを使用してメッセージを作成した後、送信請求 - 応答の送信ポートを使用してメッセージを MQSeries キューに送信します。 ポートによって、選択した一致オプションを使用して指定された URI からメッセージを受信するアダプターが指定されます。 次の操作の結果:  
  
- メッセージを取得するためのフィルター条件が満たされると、キューからメッセージが取得され、オーケストレーションに返されます。  
  
- メッセージを取得するためのフィルター条件が満たされない場合は、ダミーの応答が返されます。 これは、指定したオプションがキューからメッセージを返さなかったことを示します。  
  
  動的受信機能を使用することで、固定した受信場所が不要になるため、柔軟性が高まります。 実行時まで URI がわからない場合もあります。 動的受信機能を使用すると、メッセージの取得元を動的に決定できます。 これは、オーケストレーション内でキュー コントラクトを実装する必要がないことも意味します。  指定した一致条件に基づいて MQSeries キューから動的に指定された URI を使用することで、メッセージの取得を待機できます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|||  
|-|-|  
|ファイル|説明|  
|DynamicReceive.btproj、<br /><br /> DynamicReceive.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|DynamicReceive e.odx|アプリケーションの BizTalk オーケストレーション ファイル。|  
|Setup.bat|キー ファイルを作成し、プロジェクトをコンパイルして配置するバッチ ファイル。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 指定、 **Microsoft.XLANGs.BaseTypes.Address**ソリューションに合理的です。 変更、 **MQSeries.WaitInterval**応答メッセージの受信を予期したタイミングを指定します。 一致オプションを更新する (または追加する) またはすべてのメッセージを取得する予定の場合は、それらを削除します。  
  
## <a name="building-and-running-the-sample"></a>サンプルのビルドと実行  
  
#### <a name="to-create-the-sample"></a>サンプルを作成するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で新しいオーケストレーション プロジェクトを作成します。  
  
2. 有効にする、動的受信操作を設定して、 **MQSeries.DynamicReceive**プロパティを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを`'Yes'`します。  
  
3. 設定して、メッセージの取得元となるアドレス指定、**ポート URI**します。  
  
4. 必要に応じて、次の 2 つのプロパティを指定できます。  
  
   1.  使用して、メッセージを取得する前に待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。  
  
   2.  メッセージを受信するための一致条件を指定します。 詳細については、「一致条件」のヘルプを参照してください。  
  
5. オーケストレーションの次の変数を変更して、メッセージの取得元を指定します。  
  
   -   **キュー**、 **queueManager**、および**server**します。 これら URI を作成に使用されます、**式**図形。  
  
6. 変更、**式**図形に応じて動的キュー作成と一致オプションをコメントにします。  
  
7. 次のいずれかの方法で、プロジェクトをビルドおよび展開できます。  
  
   -   ソリューションを開き、ソリューション エクスプ ローラーでプロジェクトを右クリックしてをクリックして**プロパティ**プロジェクトのプロパティを表示します。 [署名] タブをクリックして**\<新規.\>** で、**厳密な名前キー ファイルを選択して**ボックスの一覧します。 次に、キー ファイル名を指定して展開します。  
  
   -   setup.bat ファイルを実行することもできます。このファイルは、キー ファイルを作成し、プロジェクトをビルドして展開します。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  オーケストレーションを BizTalk ホストにバインドします。  
  
2.  オーケストレーションにより作成されたファイル受信ポートを有効にします。 変更、ファイル受信場所から**c:\temp\in**適切なファイル フォルダーにします。  
  
3.  作成された 2 つの送信ポートを参加させ、開始します。 一方のポートは動的な送信要求 - 応答ポートで、もう一方はファイル送信ポートであり、メッセージが送信されるキューです。 これが正しい場所に設定されていることを確認します。  
  
4.  オーケストレーションを開始するには、入力フォルダーのファイルを削除します。 MQSeries アダプターと呼び出しが起動、 **MQSAgent2**メッセージを取得する指定されたサーバー上の COM + コンポーネント。 受信したメッセージは、ファイル送信ポートで指定されているフォルダーの場所に表示されます。  
  
5.  指定された条件に一致するメッセージがない場合、**式**図形、ダミーのメッセージが出力フォルダーにドロップします。 一致オプションを無効にするで最後の 2 つの行をコメント アウト、**式**図形。  
  
## <a name="comments"></a>コメント  
  
-   動的に作成されたキューが削除されていない場合は、次のオーケストレーション インスタンスがアクティブ化されたときにエラーが発生します。  
  
-   URI を動的に設定する方法は他にもあります。このサンプルでは、1 つのオプションのみを指定しています。 たとえば、メッセージ コンテキスト内のプロパティを読み込むことで、URI を設定できます。  
  
-   一致オプションを満たすメッセージがキューにない場合は、ダミーのメッセージが返されます。  
  
-   このサンプルでは動的送信ポートが使用されているため、再試行やトランザクションなど、他のオプションを指定する必要がある場合があります。 アダプターによって公開されるコンテキスト プロパティを使用して、メッセージを動的な送信請求 - 応答ポートに送信する前にこれらのオプションを設定します。  
  
-   MQSeries キューを作成しを使用して動的に削除、 **MQSAdapterAdmin2**インターフェイス。 MQSeries キューを動的に作成する方法の例を参照してください"Support for Queue Management" [ http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400)します。