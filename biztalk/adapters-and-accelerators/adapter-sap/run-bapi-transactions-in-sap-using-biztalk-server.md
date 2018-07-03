---
title: BizTalk Server を使用して SAP の BAPI トランザクションを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ff5cf7-5e98-4d74-a13f-4de65c215d41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67614e9ec07a2e675c0972ad4ea3429266726b56
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978675"
---
# <a name="run-bapi-transactions-in-sap-using-biztalk-server"></a>BizTalk Server を使用して SAP の BAPI トランザクションを実行します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]によりアダプターでクライアントを使用して SAP システムでトランザクションの実行に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 トランザクションのオーケストレーションを作成する前に、まずトランザクションの実行される基本的なシナリオを理解する必要があります。 トランザクションの一般的なシナリオでは、(BAPI を呼び出す) などの複数の操作で要求メッセージは、SAP システムに送信されます。 これはあると呼ばれます「操作メッセージ」 オーケストレーションは、各操作のメッセージを要求メッセージから抽出し、SAP システムに個別の操作のメッセージを送信する必要があります。 オーケストレーションに送信した後、同じ接続を使用して他の 1 つします。 オーケストレーションでは、BizTalk マップを使用して XML 変換を使用して、「操作のメッセージ」から、個々 のメッセージを抽出します。  
  
 操作を実行すると、オーケストレーションはする必要がありますをコミットするか、それぞれ BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK、メッセージを送信することによって、トランザクションを中止します。 これらが参照されます「トランザクション メッセージ」として  
  
## <a name="how-does-the-adapter-enable-transactions-through-biztalk-server"></a>アダプターが BizTalk Server を使用したトランザクションを有効する方法  
 トランザクションを使用して SAP システムを有効にする、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  
  
- メッセージ コンテキスト プロパティを開く、再利用、CLOSE、および中止を提供します。  
  
- BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK を使用して、コミットするか、操作を中止します。 これらは、SAP システムによって公開されます。  
  
  次の表では、いくつかのガイドラインを BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK プロパティを使用する方法を示します。  
  
|メッセージ|OPEN|再利用します。|CLOSE|ABORT|  
|-------------|----------|-----------|-----------|-----------|  
|最初のメッセージ (メッセージを操作する)|はい|いいえ|いいえ|いいえ|  
|後続のメッセージ (メッセージの操作)|いいえ|はい|いいえ|いいえ|  
|BAPI_TRANSACTION_COMMIT (トランザクション メッセージ)|いいえ|いいえ|はい|いいえ|  
|BAPI_TRANSACTION_ROLLBACK (トランザクション メッセージ)|いいえ|いいえ|はい|はい|  
  
 テーブルでは、"Yes"は、メッセージに使用するメッセージ コンテキスト プロパティを表します。 同様に、"No"は、メッセージで使用しないように、メッセージ コンテキスト プロパティを表します。  
  
 テーブルをまとめています。  
  
-   最初のメッセージは操作メッセージを常にする必要があり、開いているプロパティのみを使用する必要があります。  
  
-   後続の操作メッセージには、再利用するプロパティを使用する必要があります。  
  
-   BAPI_TRANSACTION_COMMIT に対応するトランザクションのコミット トランザクション メッセージでは、閉じるプロパティを使用する必要があります。  
  
-   トランザクションを中止する BAPI_TRANSACTION_ROLLBACK に対応するトランザクション メッセージでは、終了または中止のいずれかのプロパティを使用できます。 場合は、ABORT の使用、理想的には、メッセージがオーケストレーションの例外ブロックでなければなりません。  
  
## <a name="key-considerations-related-to-transactions-using-biztalk-server"></a>BizTalk Server を使用してトランザクションに関連の重要な考慮事項  
  
- オーケストレーションでは、複数の送信ポートがある場合、アダプターは自動的に各ポートから受信したメッセージのトランザクションを分離します。 つまり、トランザクションがポートにまたがることはできません。  
  
- メッセージの再試行回数は、SAP トランザクション内のメッセージに対してはサポートされていません。 そのため、ユーザーは、0 に、メッセージの再試行を設定する必要があります。  
  
- アダプターでは、前の表には、"No"としてマークされている組み合わせの望ましくない結果を生成可能性があります。 "Yes"としてマークされている組み合わせを使用する必要があります。  
  
- メッセージ コンテキスト プロパティがない、アダプターに送信されるメッセージは、現在のトランザクション コンテキストにバインドされないように通常実行されます。  
  
- BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK 理想的には、オーケストレーションでは、現在のトランザクション コンテキストの最後のメッセージはあります。  
  
  次のセクションでは、SAP を使用してトランザクションを実行する方法の手順を提供する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="how-to-perform-a-transaction-on-an-sap-system"></a>SAP システムに対してトランザクションを実行する方法でしょうか。  
 使用して SAP システムに対する演算を実行、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[SAP アプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)します。 トランザクションを実行する SAP システムで、これらのタスクは。  
  
1. BizTalk プロジェクトを作成し、トランザクションを実行する RFC のスキーマを生成します。 さらに、BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK Rfc のスキーマを生成する必要があります。  
  
2. SAP システムからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。  
  
3. 要求メッセージから個人「操作のメッセージ」を抽出し、SAP システムに送信するオーケストレーションを作成します。 要求メッセージ、に基づいてオーケストレーションも決定をコミットまたはトランザクションをロールバックするかどうか。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル SAPTransaction、このトピックの「に基づいてが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 SAP システムに対してトランザクションを実行する方法を説明するためには、次のスキーマが必要です。  
  
- 「操作のメッセージ」の SAP システムに対して操作を実行します。 アダプターに送信される要求メッセージは、このスキーマに準拠する必要があります。 操作のノードの任意の数を格納している任意のユーザー固有のスキーマを指定できます。 このトピックでは、MultipleOrders.xsd スキーマが使用されます。 付属のトランザクションのサンプルの一部としても、スキーマが用意されて、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。 詳細については、次を参照してください。[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)します。  
  
- RFC を呼び出すなどの SAP システムに対する操作を実行します。 操作を実行する要求メッセージは、このスキーマに準拠している必要があります。 使用してこのスキーマを生成する必要があります、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。 このトピックでは、BAPI_SALESORDER_CREATEFROMDAT2 RFC が呼び出されます。 RFC のスキーマを生成する方法の詳細については、次を参照してください。[参照、検索と SAP の RFC 操作のメタデータを get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)します。  
  
- 中止またはトランザクションをコミットします。 コミットまたはトランザクションを中止する要求は、このスキーマに準拠する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK RFC に commit および rollback 操作それぞれ使用します。 使用してこれらの Rfc のスキーマを生成する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
> [!NOTE]
>  必要なすべてのスキーマを BizTalk プロジェクトに追加されていることを確認する必要があります。  
> 
> [!IMPORTANT]
>  BizTalk プロパティ スキーマをへの参照を追加する必要があります[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を BizTalk プロジェクトにします。 スキーマ ファイル*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップでは、通常は\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Adapter Pack\bin です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 メッセージを作成する前に、(MultipleOrders.xsd 型) の要求メッセージに"operation"ノードの数を決定する必要があります。 この例では、BAPI_SALESORDER_CREATEFROMDAT2 RFC を呼び出す 2 つの操作のメッセージは、要求メッセージのことを想定しています。 したがって、この RFC に対して生成されたスキーマをマップする 1 つの要求-応答メッセージのセットを作成する必要があります。  
  
 BizTalk プロジェクトで、次のメッセージを作成する必要があります。  
  
- メッセージを SendtoAdapter、オーケストレーションに送信される要求メッセージ。 このメッセージは、入力メッセージ、MultipleOrders.xsd のスキーマにマップする必要があります。  
  
- メッセージ、BAPIMessage、SAP システムに送信された最初の操作。 応答メッセージ BAPIResponse、最初の操作の応答を作成することも必要があります。 要求および応答メッセージは、BAPI_SALESORDER_CREATEFROMDAT2 RFC に対して生成されたスキーマにマップする必要があります。  
  
- メッセージを BAPICommitMessage、コミット操作。 応答メッセージ BAPICommitResponse、対応する応答メッセージを作成することも必要があります。 要求および応答メッセージは、BAPI_TRANSACTION_COMMIT RFC のスキーマにマップする必要があります。  
  
- メッセージ、BAPIRollbackMessage、ロールバック操作。 応答メッセージ BAPIRollbackResponse、対応する応答メッセージを作成することも必要があります。 要求および応答メッセージは、BAPI_TRANSACTION_ROLLBACK RFC のスキーマにマップする必要があります。  
  
  メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  開いていない場合は、オーケストレーションの種類を BizTalk プロジェクトを開きます。 をクリックして**ビュー**、 をポイント**その他の Windows**、 をクリック**オーケストレーション**します。  
  
2.  **オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。  
  
3.  右クリックし、メッセージを新しく作成し、[**プロパティ] ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**SendToAdapter**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*SAPTransaction.MultipleOrders*ここで、 *SAPTransaction* BizTalk プロジェクトの名前を指定します。 *MultipleOrders*要求メッセージのスキーマです。|  
  
5.  6 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |BAPIMessage|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2*|  
    |BAPIResponse|*SAPTransaction.SAPBindingSchema.BAPI_SALESORDER_CREATEFROMDAT2Response*|  
    |BAPICommitMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMIT*|  
    |BAPICommitResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_COMMITResponse*|  
    |BAPIRollbackMessage|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACK*|  
    |BAPIRollbackResponse|*SAPTransaction.SAPBindingSchema.BAPI_TRANSACTION_ROLLBACKResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAP システムでトランザクションを実行するためです。 このオーケストレーションでの要求メッセージを削除する、定義されている受信場所。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージを使用し、SAP システムに渡します。 SAP システムからの応答は、別の場所に保存されます。  
  
 オーケストレーションを作成するときに別の考慮事項は次のとおりです。  
  
- BAPI_SALESORDER_CREATEFROMDAT2 RFC の要求メッセージのスキーマをマップします。  
  
- BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK RFC の要求メッセージのスキーマをマップします。  
  
  BizTalk マップを使用して XML 変換を使用して、スキーマをマップできます。 これを実現するには、オーケストレーションの変換図形が含まれます。  
  
  最後に、要求メッセージの情報をコミットまたは中止トランザクションにするかどうかに基づき、オーケストレーションする必要がありますを決定適切なメッセージを SAP システムに送信します。 これを実現するには、オーケストレーションの判断図形が含まれます。  
  
  オーケストレーションに含まれるさまざまな図形の詳細については、次を参照してください。、**オーケストレーション デザイナー UI** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
  SAP のトランザクションのサンプルのオーケストレーションには、次に似ています。  
  
  ![SAP でトランザクションを実行するためのオーケストレーション](../../adapters-and-accelerators/adapter-sap/media/727f82e9-51a9-4a94-9d0a-d05c17904bde.gif "727f82e9-51a9-4a94-9d0a-d05c17904bde")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、上記のオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveInputXML|Receive|-設定**名前**に*ReceiveInputXML*<br /><br /> -設定**アクティブ**に*は True。*|  
|SendToLOB|Send|-設定**名前**に*SendToLOB*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
 要求メッセージには、2 つのメッセージの挿入があるため、送信のもう 1 つのセットを作成し、受信図形のメッセージを SAP に送信して、応答を受信する必要があります。 ただし、挿入メッセージをコミットまたはロールバックする可能性があります、ため、図形の 2 番目のセットは判断ブロック内で作成する必要があります。 コミットの図形の 1 つのセットとロールバックの図形の別のセットを作成する必要があります。  
  
> [!NOTE]
>  ドラッグ アンド BizTalk オーケストレーション ツールボックスから判断図形をドロップして判断ブロックを追加できます。  
  
#### <a name="message-shapes-for-commit"></a>メッセージの構築図形をコミットします。  
 次の表では、「コミット パス」のオーケストレーションの図形を示します。 ここでは、要求メッセージの受信メッセージを作成する必要はありません。 要求メッセージは、前のメッセージ図形から渡されます。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|SendBAPICommit|Send|-設定**名前**に*SendBAPICommit*|  
|ReceiveCommitResponse|Receive|-設定**名前**に*ReceiveCommitResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse2|Send|-設定**名前**に*SendResponse2*|  
  
#### <a name="message-shapes-for-abort"></a>メッセージの構築図形を中止します。  
 オーケストレーションの「ロールバック パス」の図形を次の表に示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|SendBAPIRollback|Send|-設定**名前**に*SendBAPIRollback*|  
|ReceiveRollbackResponse|Receive|-設定**名前**に*ReceiveRollbackResponse*<br /><br /> -設定**アクティブ**に*False*|  
|SendResponse3|Send|-設定**名前**に*SendResponse3*|  
  
### <a name="setting-the-rule-expression"></a>ルール式の設定  
 コミットのメッセージの構築図形に含まれ、判断図形を追加することで判断ブロック内の操作を中止します。 オーケストレーションが決定を行うが条件を指定するには、ルール図形に式をトランザクションがいずれかがコミットまたはロールバックのベースを指定する必要があります。 たとえば、ルール図形の次の式を指定する必要があります。  
  
```  
SendToAdapter.isCommit == true  
```  
  
 ここで、SendToAdapter は、要求メッセージのスキーマ用に作成したメッセージです。 要求メッセージの場合、`isCommit`にタグが設定されている**True**、オーケストレーションは、「コミット」ルート。 それ以外の場合、オーケストレーションでは、「ロールバック」のルートがかかります。  
  
 式エディターでこの条件を指定できるようにする必要があります昇格している、`isCommit`アダプターに送信される要求メッセージのメッセージ スキーマ内のプロパティ。 このトピックでは、使用する入力のスキーマは MultipleOrders.xsd は。 昇格する必要があります、`isCommit`このスキーマのプロパティ。 プロパティを昇格させる方法についての詳細については、次を参照してください。[プロパティの昇格](../../core/promoting-properties.md)します。
  
### <a name="adding-construct-message-shapes"></a>メッセージの構築図形の構成要素を追加します。  
 前述のように、2 つの insert メッセージと、コミットまたは中止メッセージをアダプターに送信された要求メッセージが含まれます。 メッセージの構築図形を追加する必要があり、SAP システムに送信される個々 の操作メッセージの抽出を変換図形の内でします。 メッセージのトランザクションを有効にするためのコンテキスト プロパティを設定するメッセージの割り当て図形を追加することも必要があります。  
  
#### <a name="the-first-construct-message-shape"></a>最初のメッセージの構築図形  
 たとえば、最初のメッセージの構築図形には、"ReceiveXML"が呼び出されます この図形の"BAPIMessage"として構築メッセージ プロパティを指定します。 開く変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックス。  
  
- 選択すると、新しいマップを作成します。  
  
- 左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*します。  
  
- 左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPIMessage*します。  
  
- クリックして**OK**マッパーを起動します。 要求メッセージのスキーマを BAPI_SALESORDER_CREATEFROMDAT2 のスキーマにマップします。 使用することができます、**インデックス**functoid をソース スキーマと送信先スキーマ間のマップを作成します。 **インデックス**functoid では、一連のレコードの特定のレコードの情報を選択することができます。  
  
   使用してマッピングされたスキーマを次に示します、**インデックス**functoid。  
  
   ![インデックス functoid を使用してマッピングされたスキーマ](../../adapters-and-accelerators/adapter-sap/media/d0ade577-ea74-4be3-a724-4ba19397d8d3.gif "d0ade577-ea74-4be3-a724-4ba19397d8d3")  
  
   使用しての詳細については、**変換の構成**ダイアログ ボックスを参照してください、**変換の構成 ダイアログ ボックス**[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
   インデックス functoid の使用に関する詳細については、次を参照してください。[インデックス Functoid](../../core/index-functoid.md)します。
       
   スキーマをマップした後は、マップ ファイルのプロパティ ページを使用してマッピングをテストできます。 詳細については、次を参照してください。、  **<Map File>プロパティ ページ ダイアログ ボックスで、マップのテスト**タブ[!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
  メッセージの割り当て図形では、トランザクションの開始をメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティになります。  
  
```  
BAPIMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "OPEN";  
```  
  
#### <a name="the-commit-construct-message-shape"></a>コミット メッセージの構築図形  
 コミット操作のメッセージの構築図形は"CommitMessage"と呼ばれるとします この図形の"BAPICommitMessage"として構築メッセージ プロパティを指定します。 開く変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックス。  
  
- 選択すると、新しいマップを作成します。  
  
- 左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*します。  
  
- 左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPICommitMessage*します。  
  
- マッパーを起動するには、[ok] をクリックします。 要求メッセージのスキーマを BAPI_TRANSACTION_COMMIT のスキーマにマップします。 BAPI_TRANSACTION_COMMIT ノードにはレコードの階層が含まれていないためにこのマッピング インデックス functoid を含める必要はありません。  
  
  メッセージの割り当て図形では、トランザクションをコミットするメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティになります。  
  
```  
BAPICommitMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "CLOSE";  
```  
  
#### <a name="the-rollback-construct-message-shape"></a>ロールバックのメッセージの構築図形  
 たとえば、ロールバック操作のメッセージの構築図形には、"RollbackMessage"が呼び出されます この図形の"BAPIRollbackMessage"として構築メッセージ プロパティを指定します。 開く変換図形をダブルクリックして、**変換の構成** ダイアログ ボックス。 ダイアログ ボックス。  
  
- 選択すると、新しいマップを作成します。  
  
- 左側のウィンドウから次のように選択します。**ソース**との間、**変数名**ドロップダウン選択*SendToAdapter*します。  
  
- 左側のウィンドウから次のように選択します。**先**との間、**変数名**ドロップダウン選択*BAPIRollbackMessage*します。  
  
- マッパーを起動するには、[ok] をクリックします。 要求メッセージのスキーマを BAPI_TRANSACTION_ROLLBACK のスキーマにマップします。 BAPI_TRANSACTION_ROLLBACK ノードにはレコードの階層が含まれていないためにこのマッピング インデックス functoid を含める必要はありません。  
  
  メッセージの割り当て図形では、トランザクションをロールバックするメッセージ コンテキスト プロパティを指定します。 たとえば、最初のメッセージをメッセージ コンテキスト プロパティになります。  
  
```  
BAPIRollbackMessage(Microsoft.Adapters.SAP.BiztalkPropertySchema.ConnectionState) = "ABORT";  
```  
  
> [!IMPORTANT]
>  、一般的なシナリオでは、例外ブロックで BAPI_TRANSACTION_ROLLBACK に中止のコンテキスト プロパティに対応するメッセージを使用する必要があります。  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  
  
 このオーケストレーションでは、3 つのポートが作成されます。 最初のポートは、指定したフォルダーから要求メッセージを取得します。 2 番目のポートは、SAP システムに、メッセージを送信し、応答を受信します。 3 番目のポートでは、別のフォルダーへの応答を保存します。 そこで：  
  
-   最初のポートは、1 つのスキーマ、つまり、MultipleOrders.xsd のメッセージのみを受け取ります。  
  
-   2 番目のポートは、BAPI_SALESORDER_CREATEFROMDAT2 RFC のスキーマのメッセージを送受信します。 また、同じポートが使用してコミットするか、トランザクションをロールバックします。 そのため、このポートは、BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK Rfc のスキーマのメッセージも受信します。 これを有効にするのには、3 つの操作は、このポートは、特定のメッセージ スキーマに対応する各に作成されます。  
  
-   2 番目のポートと同様に、このポートもメッセージを受信する 3 つの異なるスキーマを持つ。 そのため、このポートで 3 つの操作を作成する必要は。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br /><br /> -設定**型**に*FileInType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br /><br /> -設定**型**に*LOBPortType*<br /><br /> -設定**通信パターン**に*要求-応答*<br /><br /> -設定**通信方向**に*送受信*<br /><br /> -作成操作*BAPIMessage*します。<br /><br /> -作成操作*CommitMessage*します。 この操作は、コミット メッセージを送信する使用されます。<br /><br /> -作成操作*RollbackMessage*します。 この操作は、ロールバックのメッセージを送信する使用されます。|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br /><br /> -設定**型**に*SaveResponseType*<br /><br /> -設定**通信パターン**に*一方向*<br /><br /> -設定**通信方向**に*送信*します。<br /><br /> -作成操作*BAPIMessage*します。<br /><br /> -作成操作*CommitMessage*します。 この操作は、コミット メッセージの応答を削減されます。<br /><br /> -作成操作*RollbackMessage*します。 この操作はロールバック メッセージに対する応答を保存する使用されます。|  
  
## <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveInputXML|-設定**メッセージ**に*SendToAdapter*<br /><br /> -設定**操作**に*FileIn.Transaction.Request*|  
|SendToLOB|-設定**メッセージ**に*BAPIMessage*<br /><br /> -設定**操作**に*LOBPort.BAPIMessage.Request*|  
|ReceiveResponse|-設定**メッセージ**に*BAPIResponse*<br /><br /> -設定**操作**に*LOBPort.BAPIMessage.Response*|  
|SendResponse|-設定**メッセージ**に*BAPIResponse*<br /><br /> -設定**操作**に*SaveResponse.BAPIMessage.Request*|  
|SendBAPICommit|-設定**メッセージ**に*BAPICommitMessage*<br /><br /> -設定**操作**に*LOBPort.CommitMessage.Request*|  
|ReceiveCommitResponse|-設定**メッセージ**に*BAPICommitResponse*<br /><br /> -設定**操作**に*LOBPort.CommitMessage.Response*|  
|SendResponse2|-設定**メッセージ**に*BAPICommitResponse*<br /><br /> -設定**操作**に*SaveResponse.CommitMessage.Request*|  
|SendBAPIRollback|-設定**メッセージ**に*BAPIRollbackMessage*<br /><br /> -設定**操作**に*LOBPort.RollbackMessage.Request*|  
|ReceiveRollbackResponse|-設定**メッセージ**に*BAPIRollbackResponse*<br /><br /> -設定**操作**に*LOBPort.RollbackMessage.Response*|  
|SendResponse3|-設定**メッセージ**に*BAPIRollbackResponse*<br /><br /> -設定**操作**に*SaveResponse.RollbackMessage.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
## <a name="handling-exceptions"></a>例外の処理  
 BAPI トランザクションを実行するような複雑なオーケストレーションで、オーケストレーションの状態の追跡を発生すると、問題を解決できるように、発生したエラーを報告するには重要です。 BizTalk オーケストレーションでは、トランザクション、補正、および例外処理を通じて発生する問題を解決して、オーケストレーションの状態を維持するために、エラーを処理するためのツールを提供します。  
  
 オーケストレーション デザイナーには、トランザクションと例外処理のフレームワークとして、**スコープ**図形。 スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。 1 つのスコープには、1 つ以上のブロックが含まれます。 本文が含まれると、必要に応じて、任意の数の例外処理ブロックが追加されます。 スコープでは、BAPI のトランザクションの場合、オーケストレーション全体を含めることできます (前の図を参照してください)。  
  
 例外をキャッチするには、追加する必要があります、**例外のキャッチ**をオーケストレーションにブロックします。 **例外をキャッチ**の末尾に関連付けられているブロック、**スコープ**オーケストレーション デザイナーで図形。 BAPI のトランザクションの場合は、「中止」ルーチンを追加する必要があります、**例外のキャッチ**ブロック、つまり、「中止」ルーチンに次を追加する必要があります。  
  
- (入力メッセージからの要求メッセージの抽出) を変換し (コンテキスト プロパティの設定) をメッセージの割り当て図形で構成されるメッセージの構築図形  
  
- 送信し、受信図形。  
  
  SAP トランザクションのサンプルを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)](SAPTransaction) が付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を処理する例外を示します。 サンプルの詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)します。  
  
  例外を処理する方法の詳細については、次を使用して一般に、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[トランザクションを使用して、例外処理](../../core/using-transactions-and-handling-exceptions.md)します。
  
## <a name="add-the-biztalk-property-schema-to-biztalk"></a>BizTalk プロパティ スキーマの BizTalk への追加します。  
 BizTalk プロジェクトでアセンブリを BizTalk プロパティ スキーマへの参照を追加した[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 BizTalk プロジェクトが配置されるアプリケーションは、BizTalk アプリケーションでリソースとしては、同じアセンブリを追加する必要があります。 スキーマ ファイル*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]通常セットアップ\<インストール ドライブ\>: \Program Files\Microsoft BizTalk アダプターPack\bin します。 せず、このリソースは、プロジェクトを配置することはできません。  
  
#### <a name="to-add-an-assembly-as-a-resource-in-biztalk"></a>BizTalk のリソースとしてアセンブリを追加するには  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーションでは、します。  
  
3. 右クリック**リソース**、 をポイント**追加** をクリックし、 **BizTalk アセンブリ**します。  
  
4. **リソースの追加**ダイアログ ボックスで、をクリックして**追加**、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択を順にクリックします**オープン**します。  
  
5. **オプション**、BizTalk アセンブリを GAC にインストールするためのオプションを指定し、クリックして**OK**します。  
  
   BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 アプリケーションを構成する方法の詳細については、次を参照してください。[アプリケーションを構成する方法](../../core/how-to-configure-an-application.md)します。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、SAP システムに送信します。  
  
  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションでの SAP システムからの応答を含む応答メッセージをドロップする場所の場所を定義します。  
  
  - SAP システムにメッセージを送信する物理 Wcf-custom または WCF-SAP 送信ポートを定義します。 ポートを作成する方法については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)します。 送信ポートの送信は、複数のスキーマに準拠したメッセージの送受信および 2 つの操作を実行、ためには、動的アクションの両方の操作を設定する必要があります。 アクションの詳細については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)します。 WCF カスタムを作成するときに次の重要な考慮事項に従っているか、WCF SAP トランザクションを実行するポートを送信するようにします。  
  
    |次を設定します。|この値を|  
    |-----------------------|-------------------|  
    |操作|送信ポートは、1 つ以上の操作のメッセージを送受信します。 そのため、各操作の送信ポートでアクションを設定する必要があります。<br /><br /> `<BtsActionMapping>   <Operation Name="BAPIMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_SALESORDER_CREATEFROMDAT2" />   <Operation Name="CommitMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT" />   <Operation Name="RollbackMessage" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK" /> </BtsActionMapping>`|  
    |EnableBizTalkCompatibilityMode|このバインドのプロパティを設定**True**します。|  
    |EnableConnectionPooling|このバインドのプロパティを設定**False**トランザクションを実行する前にします。 アダプターと BizTalk 間を設定するチャネルが予期せず終了のシナリオでは、対応する接続は、接続プールに追加されます。 別のチャネルが開かれ、新しいチャネルは、同じ接続オブジェクトを取得、古い接続オブジェクトでコミットされていないトランザクションは、新しいチャネル経由で、トランザクションがコミットされたときに、コミットはあります。 これを回避するには、接続プールする必要があります無効にするトランザクションの実行中にします。|  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、次を参照してください。 [sap ポートのバインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)します。
    > 
    > [!IMPORTANT]
    >  バックアップ トランスポートを構成するには WCF カスタムまたは WCF-SAP 送信ポートのプライマリ トランスポートは、関数が失敗した場合、別の SAP システムにメッセージを送信することができます。 WCF に基づいた、SAP システムでトランザクションを実行するためには、ただし、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]別の SAP サーバーを指すバックアップ トランスポートを指定することはできません。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 BizTalk アプリケーションの実行中のトランザクションに SAP システムを起動する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)、[アプリケーションを起動する方法](../../core/how-to-start-and-stop-a-biztalk-application.md)します。
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   SAP システムにメッセージを送信する Wcf-custom または WCF SAP の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後に、定義済みの場所で要求メッセージをオーケストレーションを削除する必要があります。 要求メッセージが、たとえば、MultipleOrders.xsd スキーマする特定のスキーマに従う必要があります。 たとえば、要求メッセージを SAP システムでの販売注文を作成し、操作をコミットします。  
  
```  
<ns0:Orders xmlns:ns0="http://BAPISend.MultipleOrders">  
  <Order>  
      <ORDER_HEADER_IN>  
        <DOC_TYPE>TA</DOC_TYPE>  
        <SALES_ORG>1000</SALES_ORG>  
        <DISTR_CHAN>10</DISTR_CHAN>  
        <DIVISION>00</DIVISION>  
        <SALES_OFF>1000</SALES_OFF>  
        <REQ_DATE_H>20060901</REQ_DATE_H>  
        <PURCH_DATE>20060901</PURCH_DATE>  
        <PURCH_NO_C>Cust A</PURCH_NO_C>  
        <CURRENCY>EUR</CURRENCY>  
      </ORDER_HEADER_IN>  
      <ORDER_ITEMS_IN>  
          <MATERIAL>P-109</MATERIAL>  
          <PLANT>1000</PLANT>  
          <TARGET_QU>ST</TARGET_QU>  
      </ORDER_ITEMS_IN>  
      <ORDER_PARTNERS>  
          <PARTN_ROLE>AG</PARTN_ROLE>  
          <PARTN_NUMB>0000000257</PARTN_NUMB>  
      </ORDER_PARTNERS>  
    <RETURN></RETURN>  
  </Order>  
  <isCommit>true</isCommit>  
  <BAPI_TRANSACTION_COMMIT>  
  </BAPI_TRANSACTION_COMMIT>  
</ns0:Orders>  
```  
  
 オーケストレーションはメッセージを使用し、SAP システムに送信します。 SAP システムからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 上記の要求メッセージの 2 つの応答メッセージを取得する-BAPI_SALESORDER_CREATEFROMDAT2 RFC と BAPI_TRANSACTION_COMMIT を使用して、コミット操作を呼び出すことの 1 つ。  
  
 BAPI_SALESORDER_CREATEFROMDAT2 への応答は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_SALESORDER_CREATEFROMDAT2Response xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <SALESDOCUMENT />   
  <ORDER_ITEMS_IN>  
    <BAPISDITM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <ITM_NUMBER>0</ITM_NUMBER>   
      <HG_LV_ITEM>0</HG_LV_ITEM>   
      <PO_ITM_NO />   
      ......  
    </BAPISDITM>  
  </ORDER_ITEMS_IN>  
  <ORDER_PARTNERS>  
    <BAPIPARNR xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">  
      <PARTN_ROLE>AG</PARTN_ROLE>   
      <PARTN_NUMB>0000000257</PARTN_NUMB>   
      <ITM_NUMBER>0</ITM_NUMBER>   
      ......   
    </BAPIPARNR>  
  </ORDER_PARTNERS>  
</BAPI_SALESORDER_CREATEFROMDAT2Response>  
```  
  
 BAPI_TRANSACTION_COMMIT への応答は次のとおりです。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<BAPI_TRANSACTION_COMMITResponse xmlns="http://Microsoft.LobServices.Sap/2007/03/Rfc/">  
  <RETURN>  
    <TYPE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ID xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <NUMBER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</NUMBER>   
    <MESSAGE xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <LOG_MSG_NO xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</LOG_MSG_NO>   
    <MESSAGE_V1 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V2 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V3 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <MESSAGE_V4 xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <PARAMETER xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <ROW xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/">0</ROW>   
    <FIELD xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
    <SYSTEM xmlns="http://Microsoft.LobServices.Sap/2007/03/Types/Rfc/" />   
  </RETURN>  
</BAPI_TRANSACTION_COMMITResponse>  
```  
  
> [!NOTE]
>  要求メッセージが BAPI_TRANSACTION_ROLLBACK RFC を呼び出す場合は、2 番目の応答が BAPI_TRANSACTION_ROLLBACK 用になります。  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 BizTalk Server を使用した SAP システムでトランザクションを実行中に発生する可能性が、例外については、次を参照してください。[例外とエラーは、SAP アダプターを使用した処理](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成すると、送信ポートを作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定ファイルからインポートできます。 バインド ファイルの詳細については、次を参照してください。[再利用の SAP アダプター バインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)します。  
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)