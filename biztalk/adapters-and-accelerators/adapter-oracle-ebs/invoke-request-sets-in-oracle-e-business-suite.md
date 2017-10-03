---
title: "Oracle E-business Suite での要求のセットを呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a79bff63-325d-4745-ab0e-839e00476ab1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924bfbfc8e0d22ba5fb00099039b21a5b8180bcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-request-sets-in-oracle-e-business-suite"></a>Oracle E-business Suite での要求のセットをを呼び出す
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で要求のセットを実行できます。 セットは、1 つまたは複数の段階的に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 を要求します。 アダプターが要求のセットをサポートする方法の詳細については、次を参照してください。[要求設定に対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)です。 要求のセットを呼び出すためのメッセージを SOAP の構造に関する情報を参照してください[要求の設定のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 内の手順を完了する必要があります[Oracle E-business Suite アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)です。  
  
## <a name="how-to-invoke-request-sets-in-oracle-e-business-suite"></a>Oracle E-business Suite で要求を呼び出す方法を設定します。  
 Oracle E-business Suite を使用して、操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 要求を呼び出すには、これらのタスクは。  
  
-   BizTalk プロジェクトを作成し、呼び出し先によって要求セットのスキーマを生成します。  
  
-   Oracle E-business Suite から送信してメッセージの送受信用の BizTalk プロジェクトでメッセージを作成します。  
  
-   要求のセットを呼び出すオーケストレーションを作成します。  
  
-   構築し、BizTalk プロジェクトを展開します。  
  
-   BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
-   BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックを呼び出すことによって、要求セットを呼び出す方法を示します、**関数セキュリティ レポート**から (表示名) の要求の設定、**アプリケーション オブジェクト ライブラリ**アプリケーションです。 実際の要求セットの名前は**FNDRSSUB43**です。 この要求のセットは、既定の Oracle E-business Suite アプリケーションで使用できます。 この要求のセットを返します要求 id です。  
  
 そのため、このトピックではお用スキーマを生成、 **FNDRSSUB43**セットを要求します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法についての詳細。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 今すぐ、オーケストレーションのメッセージを作成して、前の手順で生成したスキーマにリンクします。  
  
 このオーケストレーションでは、2 つのメッセージを作成する必要があります: 1 つを呼び出す要求セットと要求セットの応答を受信するメッセージを送信します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *RequestSet.OracleEBSBindingRequestSets_FND です。FNDRSSUB43*RequestSet は、BizTalk プロジェクトの名前。 OracleEBSBindingRequestSets は呼び出しの生成スキーマ、 **FNDRSSUB43**セットを要求します。|  
  
6.  手順 3 を繰り返して、メッセージを作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |応答|*RequestSet.OracleEBSBindingRequestSets_FND です。FNDRSSUB43Response*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での要求のセットを呼び出すためです。 このオーケストレーションで削除する要求メッセージに、定義されている受信場所。 オーケストレーションは、このメッセージを消費しを呼び出すための Oracle E-business Suite に渡します、 **FNDRSSUB43**セットを要求します。 要求セットの応答には、Oracle から受信したされ、別の場所に保存されます。 要求のセットを呼び出すための一般的なオーケストレーションにが含まれます。  
  
-   Oracle E-business Suite にメッセージを送信し、応答を受信する図形を送受信します。  
  
-   Oracle E-business Suite に送信する要求メッセージを受信するポートは一方向の受信します。  
  
-   Oracle E-business Suite に要求メッセージを送信し、応答を受信するポートを双方向に送信します。  
  
-   Oracle E-business Suite からフォルダーに、応答を送信する一方向の送信ポートです。  
  
 要求のセットを起動するサンプル オーケストレーションには、次のようになります。  
  
 ![要求セットを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ea161292-8613-4c0b-ac24-2f26c54bf3a3.gif "ea161292-8613-4c0b-ac24-2f26c54bf3a3")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 示されている名前、*図形*列が上記のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認してください。 示されている名前、*ポート*オーケストレーションで表示される、列が、ポートの名前を示します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表は、プロパティと、メッセージのアクション図形およびポートにリンクすることを指定するために設定するには、その値を指定します。 示されている名前、*図形*列が以前のオーケストレーションで表示される、メッセージの構築図形の名前を示します。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.RequestSet.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.RequestSet.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.RequestSet.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.RequestSet.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで以前に作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 アプリケーションの構成の詳細については、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle E-business Suite に送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することもあります。 送信ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。  
  
         要求を呼び出すための設定を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーション コンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のすべての操作のアプリケーション コンテキストを指定する特定のバインディング プロパティを提供します。 要求のセットを呼び出すために使用する Wcf-custom または Wcf-oracleebs ポートでは、これらのバインディング プロパティを設定する必要があります。  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**、し、アプリケーションのコンテキストを設定する次のバインドのプロパティを指定する必要があります。  
  
            |プロパティのバインド|値|  
            |----------------------|-----------|  
            |**OracleUserName**|Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を格納しているユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OraclePassword**|Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるパスワード * とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OracleEBSResponsibilityName**|Oracle E-business Suite ユーザーに関連付けられた役割。|  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合の値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
        > [!NOTE]
        >  アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 要求のセットを呼び出すための BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs する送信ポートを呼び出し、 **FNDRSSUB43**要求セットが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 呼び出すためのスキーマに準拠した要求メッセージを削除する必要があります、アプリケーションを実行した後、 **FNDRSSUB43**セットを要求します。 など、要求メッセージを呼び出し、 **FNDRSSUB43**要求セットは。  
  
```  
<FNDRSSUB43 xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <StartTime>\</ StartTime>  
  <All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
    <FNDMNNAV xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</Responsibility>  
      \<ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">\</ns3:Application>  
    \</ns2:FNDMNNAV>  
    \<ns2:FNDMNMNU xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      \<ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator\</ns3:Responsibility>  
      \<ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">\</ns3:Application>  
    \</ns2:FNDMNMNU>  
    \<ns2:FNDMNFUN xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      \<ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator\</ns3:Responsibility>  
      \<ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">\</ns3:Application>  
    \</ns2:FNDMNFUN>  
  \</ns0:All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
\</ns0:FNDRSSUB43>  
```  
  
> [!NOTE]
>  要求のセットを呼び出すための要求メッセージには、SetRelClassOptions、SetPrintOptions、SetRepeatOptions、SetNlsOptions などの省略可能なパラメーターが必要です。 ここで指定した要求メッセージには、これらの省略可能なパラメーターがありません。 省略可能なパラメーターを含む、完全な要求メッセージに関する情報を参照してください。[要求セットのメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)です。  
  
 オーケストレーションはメッセージを処理する Oracle E-business Suite に渡します、および、応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 応答、 **FNDRSSUB43**要求のセット、次のようになります。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<FNDRSSUB43Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <FNDRSSUB43Result>2543208</FNDRSSUB43Result>  
</FNDRSSUB43Response>  
```  
  
 Oracle E-business Suite からの応答には、要求 ID が含まれています。 要求があることを意味 ID '0'、最後は failed に設定する要求で操作を送信します。 このような場合は、他の省略可能な要求などのメッセージ、ContinueOnFail、障害の原因を確認し、さらにデバッグするパラメータを指定できます。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成したできるように、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありません、ファイルから構成設定をインポートすることができます。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)