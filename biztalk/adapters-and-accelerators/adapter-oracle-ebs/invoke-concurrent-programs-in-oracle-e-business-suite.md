---
title: "Oracle E-business Suite での同時実行プログラムを起動 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85c55a35-bee4-4b50-8b00-e4198ad4c2af
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0991ab2714ddb7acc22161ffcd29179ff7339c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite"></a>Oracle E-business Suite での同時実行プログラムを呼び出す
Oracle E-business Suite では、Oracle アプリケーションで特定の操作を実行する実行可能な同時実行プログラムを公開します。 各 Oracle アプリケーションでは、一連の標準的な同時実行プログラム (同じすべての操作で) と Oracle アプリケーションに固有の特定の同時実行プログラムがあります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが呼び出すことのできる操作としてすべての同時実行プログラムを公開します。 アダプターで同時実行プログラムをサポートする方法の詳細については、次を参照してください。[同時実行プログラムで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)です。 同時実行プログラムを起動するためのメッセージを SOAP の構造に関する情報を参照してください[同時実行プログラムのメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)です。  
  
> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すには、ユーザーは、値を必要とする同時実行プログラムのパラメーターを確認する Oracle E-business Suite のマニュアルを参照され、それらを指定する必要があります。 このような同時実行プログラムの例は**Journal インポート**(実際の名前: **GLLEZL**) で、**元帳**アプリケーションです。  
  
## <a name="prerequisites"></a>前提条件  
 内の手順を完了する必要があります[Oracle E-business Suite アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)です。
  
## <a name="how-to-invoke-concurrent-programs-in-oracle-applications"></a>Oracle アプリケーションで同時実行プログラムを起動する方法  
 Oracle E-business Suite を使用して、操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明した手順のタスクでは、 [Oracle E-business Suite アプリケーションを作成するビルド ブロック](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)です。 同時実行プログラムを呼び出すには、これらのタスクです。  
  
-   BizTalk プロジェクトを作成し、同時実行プログラムを呼び出し先のスキーマを生成します。  
  
-   Oracle E-business Suite から送信してメッセージの送受信用の BizTalk プロジェクトでメッセージを作成します。  
  
-   同時実行プログラムを起動するためのオーケストレーションを作成します。  
  
-   構築し、BizTalk プロジェクトを展開します。  
  
-   BizTalk アプリケーションを作成する物理送信ポートと受信ポートを構成します。  
  
-   BizTalk アプリケーションを起動します。  
  
 このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックを呼び出す方法を示します、**顧客インターフェイス**から同時実行プログラム、**債権**アプリケーションです。 このアプリケーションは、既定の Oracle E-business Suite アプリケーションで使用できます。 この同時実行プログラムが要求 ID を返します 同時実行プログラムの状態を確認するを実行、 **Get_Status**の応答で受信した要求 ID を渡すことによって同時実行プログラム、**顧客インターフェイス**同時実行プログラムです。  
  
 このトピックでは両方のスキーマを生成して、**顧客インターフェイス**と**Get_Status**同時実行プログラムです。 スキーマを生成する方法の詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)です。  
  
## <a name="defining-messages-and-message-types"></a>メッセージとメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 今すぐ、オーケストレーションのメッセージを作成して、前の手順で生成したスキーマにリンクします。  
  
 このオーケストレーションでは、4 つのメッセージを作成する必要があります: 1 つの受信-応答の設定を呼び出す、**顧客インターフェイス**同時実行プログラムおよびその他の受信-応答呼び出しに設定、 **Get_Status**同時実行プログラムです。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。  
  
2.  まだ開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。  
  
3.  オーケストレーション ビューで右クリック**メッセージ**、クリックして**新しいメッセージ**です。  
  
4.  新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。  
  
5.  **プロパティ**のウィンドウ、 **Message_1**を次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージの種類|ドロップダウン リストから、展開**スキーマ**、し、 *ConcurrentProgram.OracleEBSBindingSchema.RACUST*ConcurrentProgram は、BizTalk プロジェクトの名前。 OracleEBSBindingSchema は呼び出しの生成スキーマ、**顧客インターフェイス**同時実行プログラムです。 **注:** RACUST は実際の名前、**顧客インターフェイス**同時実行プログラムです。 中に、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]フレンドリ名が表示されます (**顧客インターフェイス**)、スキーマには、同時実行プログラムの実際の名前が含まれています。|  
  
6.  手順 3 を繰り返して次の 3 つの新しいメッセージを作成します。 **プロパティ**新しいメッセージ ウィンドウ、次の操作します。  
  
    |識別子に設定します。|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*ConcurrentProgram.OracleEBSBindingSchema.RACUSTResponse*|  
    |Get_StatusRequest|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgram*|  
    |Get_StatusResponse|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgramResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションを設定します。  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での同時実行プログラムを起動するためです。 このオーケストレーションで削除する要求メッセージに、定義されている受信場所。 オーケストレーションは、このメッセージを消費しを呼び出すための Oracle E-business Suite に渡します、**顧客インターフェイス**同時実行プログラムです。 同時実行プログラムの応答は、Oracle から受信したされ、別の場所に保存されます。 応答メッセージには、要求 ID が含まれています。 オーケストレーションが含まれています、**メッセージの構築**を応答から要求 ID を抽出しのスキーマに準拠したメッセージの構築図形、 **Get_Status**同時実行プログラムです。 呼び出すメッセージ、 **Get_Status**同時実行プログラムは、パラメーターと要求 ID を持つ Oracle E-business Suite に送信します。 送信が含まれてし、図形、メッセージの構築図形、および Oracle にメッセージを送信し、応答を受信するポートを受信する必要があります。  
  
 通常、**顧客インターフェイス**を実行する前に待機する必要がありますプログラム同時で実行するには時間がかかり、 **Get_Status**同時実行します。 追加することでこれを自動化することができます、**遅延**図形です。  
  
 サンプル オーケストレーションには、次のようになります。  
  
 ![プログラムを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a02e9d8-8ea8-4898-8d05-c060761f4feb.gif "2a02e9d8-8ea8-4898-8d05-c060761f4feb")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 示されている名前、**図形**列は、上記のオーケストレーションに表示されるメッセージの構築図形に対応します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
|SendGetStatus|Send|-設定**名前**に*SendGetStatus*|  
|ReceiveStatusResponse|Receive|-設定**名前**に*ReceiveStatusResponse*<br />-設定**アクティブ**に*False*|  
|SaveStatusResponse|Send|-設定**名前**に*SaveStatusResponse*|  
  
### <a name="adding-a-delay-shape"></a>遅延図形を追加します。  
 場合は、オーケストレーションを呼び出すまでの待機時間を**顧客インターフェイス**と**Get_Status**同時実行のプログラム、追加する必要あります、**遅延**オーケストレーションへの図形です。 追加する必要があります、**遅延**図形のオーケストレーションへの応答のコピーされた後に、**顧客インターフェイス**をファイルにプログラムを同時に送信ポート。 そのため、追加する必要があります、**遅延**図形の後に、 **SendResponse**図形です。  
  
 内で、**遅延**図形、オーケストレーション必要があります待機する対象の処理を続行する前に、式のエディターに次のコードを追加することで、時間間隔を指定することができます、**遅延**図形。  
  
```  
new System.TimeSpan(0,2,0)  
```  
  
 このコードを追加すると、オーケストレーションは、続行する前に 2 分間待機します。 構成する方法について、**遅延**図形は、「[遅延図形を構成する方法](../../core/how-to-configure-the-delay-shape.md)です。  
  
### <a name="adding-the-construct-message-shape"></a>メッセージの構築図形を追加します。  
 Oracle E-business Suite からの応答、**顧客インターフェイス**プログラム同時には、要求 ID が含まれています。 同時実行プログラムのステータスを取得するには、パラメーターとして同じ要求 ID を渡す必要があります、 **Get_Status**同時実行プログラムです。 実行するためには、オーケストレーションで含める必要があります、**メッセージの構築**図形、およびその、**メッセージの割り当て**図形です。 目的、**メッセージの構築**図形は。  
  
-   受信した応答からの要求 ID を抽出する、**顧客インターフェイス**同時実行プログラムです。  
  
-   メッセージ スキーマに準拠したメッセージを構築するために、 **Get_Status**同時実行プログラムです。  
  
 **メッセージの構築**図形は、設定、**メッセージ構築**プロパティを**Get_StatusRequest**です。  
  
 **メッセージの割り当て**図形を追加の下。 コードを追加する前にする必要があります。  
  
```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<GetStatusForConcurrentProgram xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR'><RequestId /></GetStatusForConcurrentProgram>");  
Get_StatusRequest = XmlDoc;  
Get_StatusRequest.RequestId = xpath(Response,"string(/*[local-name()='RACUSTResponse']/*[local-name()='RACUSTResult']/text())");  
```  
  
### <a name="adding-ports"></a>ポートの追加  
 ポートを構成するのには、次の表の次の論理ポートの各プロパティを指定します。 示されている名前、*ポート*列は、オーケストレーションに表示されるポートの名前に対応します。  
  
|ポート|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*<br />操作を作成する*Cust_Interface*です。 この操作はの使用、**顧客インターフェイス**プログラム同時です。<br />操作を作成する*Get_Status*です。 この操作はの使用、 **Get_Status**同時実行プログラムです。|  
|LOBPort_GetStatus|-設定**識別子**に*LOBPort_GetStatus*<br />-設定**型**に*LOBPort_GetStatusType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
  
### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、メッセージのアクション図形とポートにリンクすることを指定するプロパティの値を指定します。 示されている名前、**図形**列は、オーケストレーション ダイアグラムに表示されるメッセージの構築図形の名前に対応します。  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Cust_Interface.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBport.Cust_Interface.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBport.Cust_Interface.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Cust_Interface.Request*|  
|SendGetStatus|-設定**メッセージ**に*Get_StatusRequest*<br />-設定**操作**に*LOBPort_GetStatus.Get_Status.Request*|  
|ReceiveStatusResponse|-設定**メッセージ**に*Get_StatusResponse*<br />-設定**操作**に*LOBPort_GetStatus.Get_Status.Response*|  
|SaveStatusResponse|-設定**メッセージ**に*Get_StatusResponse*<br />-設定**操作**に*ResponseOut.Get_Status.Request*|  
  
 これらのプロパティを指定した後、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 これで、BizTalk ソリューションをビルドしして、BizTalk Server に展開する必要があります。 詳細については、次を参照してください。[のビルドおよび実行されているオーケストレーション](../../core/building-and-running-orchestrations.md)です。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 以前に作成したオーケストレーションが下に表示、BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール アプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)です。  
  
 アプリケーションの構成が含まれます。  
  
-   アプリケーションのホストを選択します。  
  
-   物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 このオーケストレーションの次の操作を行う必要があります。  
  
    -   ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポート上の場所を定義します。 BizTalk オーケストレーションは、要求メッセージを消費し、Oracle E-business Suite に送信します。  
  
    -   ハード ディスクと、対応する file ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所に場所を定義します。  
  
    -   Wcf-oracleebs 送信ポートを 2 つの物理 Wcf-custom を定義または: を実行する Oracle E-business Suite にメッセージを送信する 1 つ、**顧客インターフェイス**同時実行プログラムで、もう一方を実行する、 **Get_Status**同時実行プログラムです。 送信ポートでアクションを指定することもあります。 ポートを作成する方法については、次を参照してください。 [Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)です。  
  
         使用して同時実行プログラムを起動する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーション コンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のすべての操作のアプリケーション コンテキストを指定する特定のバインディング プロパティを提供します。 同時実行プログラムを起動するために使用する Wcf-custom または Wcf-oracleebs のポートでは、これらのバインディング プロパティを設定する必要があります。  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**、し、アプリケーションのコンテキストを設定する次のバインドのプロパティを指定する必要があります。  
  
            |プロパティのバインド|値|  
            |----------------------|-----------|  
            |**OracleUserName**|Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるユーザー名 * とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を格納しているユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OraclePassword**|Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力する値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準的な規則を使用して Oracle E-business Suite に渡されるパスワード * とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。|  
            |**OracleEBSResponsibilityName**|Oracle E-business Suite ユーザーに関連付けられた役割。|  
  
        -   場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合の値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  
  
         異なるバインディングのプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Oracle E-business Suite バインド プロパティ読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
        > [!NOTE]
        >  アプリケーション コンテキストを設定するには、バインドのプロパティを指定することによって、またはメッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 バインドのプロパティを設定する方法の手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法の手順については、次を参照してください。 [Oracle E-business suite アプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)です。  
  
        > [!NOTE]
        >  使用してスキーマを生成する、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] (着信) の受信ポートを (発信) の送信ポートを作成または管理コンソールです。 詳細については、次を参照してください。[を構成する物理ポートのバインドを使用して、ポートのバインド ファイルを Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 同時実行プログラムを呼び出す前に、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションの起動方法の詳細については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)です。  
  
 この段階で確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs する送信ポートを呼び出し、**顧客インターフェイス**同時実行プログラムが実行されています。  
  
-   Wcf-custom または Wcf-oracleebs する送信ポートを呼び出し、 **Get_Status**同時実行プログラムが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 呼び出すためのスキーマに準拠した要求メッセージを削除する必要があります、アプリケーションを実行した後、**顧客インターフェイス**同時実行プログラムです。 など、要求メッセージを呼び出し、**顧客インターフェイス**同時実行プログラムします。  
  
```  
<RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <Description>Customer Interface Program</Description>  
  <StartTime></StartTime>  
  <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
  <ORG_ID>203</ORG_ID>  
</RACUST>  
```  
  
> [!NOTE]
>  同時実行プログラムを起動するため、要求メッセージには、SetOptions、SetPrintOptions、SetRepeatOptions などの省略可能なパラメーターが必要です。 ここで指定した要求メッセージには、これらの省略可能なパラメーターがありません。 省略可能なパラメーターを含む、完全な要求メッセージに関する情報を参照してください。[同時実行プログラムのメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)です。  
  
 オーケストレーションはメッセージを処理する Oracle E-business Suite に渡します、および、応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 お客様のインターフェイスの同時実行プログラムの応答には、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<RACUSTResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <RACUSTResult>2794708</RACUSTResult>  
</RACUSTResponse>  
```  
  
 Oracle E-business Suite からの応答には、要求 ID が含まれています。 オーケストレーションは応答メッセージから要求 ID を抽出しを呼び出すメッセージを構築、 **Get_Status**同時実行プログラムを実行する Oracle E-business Suite に渡します、 **Get_Status。**同時実行プログラムです。 番目の応答の受信後に**Get_Status**同時実行のプログラムは、最初の応答として同じファイルの場所にコピーします。 応答、 **Get_Status**同時実行プログラム、次のようになります。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<GetStatusForConcurrentProgramResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <GetStatusForConcurrentProgramResult>true</GetStatusForConcurrentProgramResult>   
  <Phase>Pending</Phase>   
  <Status>Standby</Status>   
  <DevPhase>PENDING</DevPhase>   
  <DevStatus>STANDBY</DevStatus>   
  <Message>null</Message>   
</GetStatusForConcurrentProgramResponse>  
```  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開して、BizTalk プロジェクトを構成することが後、は、バインド ファイルと呼ばれる XML ファイルに構成設定をエクスポートできます。 バインド ファイルを生成した後、構成設定をインポートするには、ファイルから、項目がなどの送信ポートと、同じオーケストレーションの受信ポートを作成する必要はありません。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business Suite でアダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)です。  
  
## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)