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
ms.openlocfilehash: 38cde24f8bc91fc5a2fc741978ebfac9d7283c51
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350610"
---
# <a name="dynamicreceive-sample-biztalk-server-sample"></a>DynamicReceive サンプル (BizTalk Server サンプル)
DynamicReceive サンプルでは、受信[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries からメッセージ キュー MQSeries キューの URI を動的に指定します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルで指定された MQSeries キューを動的に作成する、 **queueManager**、**キュー**、および**server**変数。 これにより、動的なシナリオを受信し、取得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で指定したフィルター条件に基づいて動的に指定された MQSeries キューからメッセージを**MQMD_MsgId**と**MQMD_CorrelId**メッセージ プロパティ。  
  
## <a name="how-this-sample-was-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 MQSeries アダプターはメッセージをオーケストレーションで、キューの URI アドレスを指定することで、MQSeries キューから受信動的にできます。 この機能は、オーケストレーションの送信請求-応答送信ポートを使用して実現されます。  
  
 動的にメッセージを受信するでは、次を指定します、**式**オーケストレーションの図形。  
  
1. 次のプロパティを設定の受信を有効にする動的、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ。**MQSeries.DynamicReceive** = `'Yes'`  
  
2. ポート URI を設定して、メッセージの取得元のアドレスを指定します。 必要に応じて、次のように指定できます。  
  
   -   使用して、メッセージを取得する前に、待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。  
  
   -   メッセージを受信するための一致条件を指定します。 一致条件のオプションは**メッセージ ID**、 **CorrelationID**、 **GroupID**、および**MessageSequenceNumber**します。 「プロパティ Related to BizTalk Server」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=89396 ](http://go.microsoft.com/fwlink/?LinkId=89396)の詳細。  
  
   これらのプロパティで、メッセージが作成された後、送信請求-応答の送信ポートを使用して MQSeries キューに送信されます。 ポートは、一致オプションを使用して、指定した URI からメッセージを受信アダプターを指定します。 次の操作の結果:  
  
- メッセージを取得するフィルター条件が満たされている場合、メッセージはキューから取得され、オーケストレーションに返されます。  
  
- メッセージを取得するフィルター条件が満たされない場合は、ダミーの応答が返されます。 これは、指定したオプション返さなかったことのすべてのメッセージ キューからを示します。  
  
  機能の提供をさらに柔軟のため、固定した受信場所必要はありませんが表示される動的を使用します。 場合によってを知らなくても、URI 実行時までです。 動的受信機能メッセージを取得する場所からを動的に決定することができます。 また、オーケストレーション内でキュー コントラクトを実装する必要はありません。  指定した一致条件に基づいて MQSeries キューから動的に指定された URI を使用してメッセージを取得するを待機することができます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*Samples Path*\>\Samples\AdaptersUsage\MQSeriesAdapter\DynamicReceive  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|||  
|-|-|  
|ファイル|説明|  
|DynamicReceive.btproj,<br /><br /> DynamicReceive.sln|アプリケーションのプロジェクトおよびソリューション ファイル。|  
|DynamicReceive e.odx|アプリケーションの BizTalk オーケストレーション ファイル。|  
|Setup.bat|キー ファイルを作成、プロジェクトをコンパイルしてデプロイするバッチ ファイルです。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 指定、 **Microsoft.XLANGs.BaseTypes.Address**ソリューションに合理的です。 変更、 **MQSeries.WaitInterval**応答メッセージの受信を予期したタイミングを指定します。 一致オプションを更新する (または追加する) またはすべてのメッセージを取得する予定の場合は、それらを削除します。  
  
## <a name="building-and-running-the-sample"></a>ビルドとサンプルを実行します。  
  
#### <a name="to-create-the-sample"></a>サンプルを作成するには  
  
1. Microsoft で新しいオーケストレーション プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
2. 有効にする、動的受信操作を設定して、 **MQSeries.DynamicReceive**プロパティを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを`'Yes'`します。  
  
3. 設定して、メッセージの取得元となるアドレス指定、**ポート URI**します。  
  
4. 必要に応じて次の 2 つのプロパティを指定できます。  
  
   1.  使用して、メッセージを取得する前に待機間隔を指定、 **MQSeries.WaitInterval**メッセージのプロパティ。  
  
   2.  メッセージを受信するための一致条件を指定します。 詳細については、「オプションに一致する」のヘルプを参照してください。  
  
5. オーケストレーションからメッセージを取得する場所を指定するには、次の変数を変更します。  
  
   -   **キュー**、 **queueManager**、および**server**します。 これら URI を作成に使用されます、**式**図形。  
  
6. 変更、**式**図形に応じて動的キュー作成と一致オプションをコメントにします。  
  
7. ビルドして、次の方法のいずれかでプロジェクトを配置します。  
  
   -   ソリューションを開き、ソリューション エクスプ ローラーでプロジェクトを右クリックしてをクリックして**プロパティ**プロジェクトのプロパティを表示します。 [署名] タブをクリックして**\<新規.\>** で、**厳密な名前キー ファイルを選択して**ボックスの一覧します。 キー ファイル名を指定し、デプロイします。  
  
   -   または、キー ファイルを作成し、プロジェクトをビルドし、それを展開する setup.bat ファイルを実行します。  
  
#### <a name="to-run-the-sample"></a>サンプルを実行するには  
  
1.  BizTalk ホストにオーケストレーションをバインドします。  
  
2.  により、ファイルは、オーケストレーションによって作成されたポートを受信できます。 変更、ファイル受信場所から**c:\temp\in**適切なファイル フォルダーにします。  
  
3.  参加させ、作成された 2 つの送信ポートを開始します。 1 つのポートと動的な送信請求-応答ポートの種類は file 送信ポートをメッセージの送信先キューには、その他。 これが、適切な場所に設定されていることを確認します。  
  
4.  オーケストレーションは、開始するには、入力フォルダーにファイルをドロップします。 MQSeries アダプターと呼び出しが起動、 **MQSAgent2**メッセージを取得する指定されたサーバー上の COM + コンポーネント。 File 送信ポートで指定されたフォルダーの場所で受信したメッセージが表示されます。  
  
5.  指定された条件に一致するメッセージがない場合、**式**図形、ダミーのメッセージが出力フォルダーにドロップします。 一致オプションを無効にするで最後の 2 つの行をコメント アウト、**式**図形。  
  
## <a name="comments"></a>コメント  
  
-   キューが作成される場合に動的に、削除ですが、エラーになります次のオーケストレーション インスタンスがアクティブになります。  
  
-   URI を動的に設定するには、その他の方法があります。このサンプルでは、1 つのオプションを指定します。 たとえば、URI を設定して、メッセージ コンテキストのプロパティを読み込むことでした。  
  
-   一致オプションに適合する、キュー内のメッセージがない場合は、ダミーのメッセージが返されます。  
  
-   このサンプルでは、動的送信ポートを使用するため、その他のオプションは、再試行やトランザクションなど、指定する必要があります。 動的な送信請求-応答ポートにメッセージを送信する前にこれらのオプションを設定するのにには、アダプターによって公開されるコンテキスト プロパティを使用します。  
  
-   MQSeries キューを作成しを使用して動的に削除、 **MQSAdapterAdmin2**インターフェイス。 MQSeries キューを動的に作成する方法の例を参照してください"Support for Queue Management" [ http://go.microsoft.com/fwlink/?LinkId=89400](http://go.microsoft.com/fwlink/?LinkId=89400)します。