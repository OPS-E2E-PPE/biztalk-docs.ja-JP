---
title: Oracle E-business Suite での同時実行プログラムを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85c55a35-bee4-4b50-8b00-e4198ad4c2af
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f63efda0809a16335d8653e67b4bc1ec8987863
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375452"
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite"></a>Oracle E-business Suite での同時実行プログラムを起動します。
Oracle E-business Suite では、Oracle のアプリケーションで特定の操作を実行する実行可能な同時実行プログラムを公開します。 各 Oracle アプリケーションでは、標準の同時実行プログラム (つまり同じすべての操作では) と Oracle アプリケーションに固有の特定の同時実行プログラムのセットがあります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプター クライアントが呼び出すことができる操作としてすべての同時実行プログラムを公開します。 アダプターが同時実行プログラムをサポートする方法の詳細については、次を参照してください。[同時実行プログラムに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)します。 同時実行プログラムを呼び出すためのメッセージを SOAP の構造についてを参照してください。[同時実行プログラムのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)します。  

> [!NOTE]
>  そのメタデータを公開しない同時実行プログラム、については、Oracle E-business アダプターは、これらの同時実行プログラムごとに 100 の省略可能なパラメーターを公開します。 これらの同時実行プログラムを正常に呼び出すは、ユーザーは、値を必要とする同時実行プログラムのパラメーターを把握する Oracle E-business Suite のドキュメントを参照して、それらを指定する必要があります。 このような同時実行プログラムの例は、 **Journal インポート**(実際の名前。**GLLEZL**) で、**総勘定元帳**アプリケーション。  

## <a name="prerequisites"></a>前提条件  
 」の手順を完了する必要があります[Oracle E-business Suite のアプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)します。

## <a name="how-to-invoke-concurrent-programs-in-oracle-applications"></a>Oracle のアプリケーションで同時実行プログラムを呼び出す方法  
 Oracle E-business Suite を使用して、操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 これらのタスクは同時実行プログラムを呼び出すには。  

- BizTalk プロジェクトを作成し、同時実行プログラム、呼び出し先のスキーマを生成します。  

- Oracle E-business Suite からの送信とメッセージの送受信用の BizTalk プロジェクトでは、メッセージを作成します。  

- 同時実行プログラムを起動するためのオーケストレーションを作成します。  

- ビルドし、BizTalk プロジェクトを配置します。  

- BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

- BizTalk アプリケーションを起動します。  

  このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックを呼び出す方法を示します、**顧客インターフェイス**から同時実行プログラム、 **Receivables**アプリケーション。 このアプリケーションは、既定の Oracle E-business Suite アプリケーションで使用できます。 この同時実行プログラムは、要求 ID を返します 同時実行プログラムの状態を確認するには、実行、 **Get_Status**の応答で受信した要求 ID を渡すことによって、同時実行プログラム、**顧客インターフェイス**同時実行プログラム。  

 このトピックでは、両方のスキーマを生成しました、**顧客インターフェイス**と**Get_Status**同時実行プログラム。 スキーマを生成する方法の詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)します。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションでは、メッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  

 このオーケストレーションでは、4 つのメッセージを作成する必要があります: 1 つの受信-応答の設定を呼び出す、**顧客インターフェイス**同時実行プログラムと、その他の受信-応答の設定を呼び出す、 **Get_Status**同時実行プログラム。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1. オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  

2. 開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  

3. オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  

4. 新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  

5. **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  


   |   プロパティ   |                                                                                                                                                                                                                                                                                           目的                                                                                                                                                                                                                                                                                           |
   |--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  [Identifier]  |                                                                                                                                                                                                                                                                                         「`Request`」と入力します。                                                                                                                                                                                                                                                                                         |
   | メッセージ型 | ドロップダウン リストから展開**スキーマ**、し、 *ConcurrentProgram.OracleEBSBindingSchema.RACUST*ConcurrentProgram は、BizTalk プロジェクトの名前です。 OracleEBSBindingSchema が呼び出すために生成されたスキーマ、**顧客インターフェイス**同時実行プログラム。 **注:** RACUST は実際の名前、**顧客インターフェイス**同時実行プログラム。 中に、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]フレンドリ名が表示されます (**顧客インターフェイス**)、スキーマには、同時実行プログラムの実際の名前が含まれています。 |


6. 次の 3 つの新しいメッセージを作成する手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

   |識別子を設定するには|メッセージの種類を設定|  
   |-----------------------|-------------------------|  
   |応答|*ConcurrentProgram.OracleEBSBindingSchema.RACUSTResponse*|  
   |Get_StatusRequest|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgram*|  
   |Get_StatusResponse|*ConcurrentProgram.OracleEBSBindingSchema1.GetStatusForConcurrentProgramResponse*|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での同時実行プログラムを呼び出すためです。 要求メッセージをこのオーケストレーションで削除する、定義されている受信場所。 オーケストレーションがこのメッセージを使用し、それを呼び出すための Oracle E-business Suite に渡します、**顧客インターフェイス**同時実行プログラム。 同時実行プログラムの応答は、Oracle から受信され、別の場所に保存されます。 応答メッセージには、要求 ID が含まれています。 オーケストレーションが含まれています、**メッセージの構築**を応答からの要求 ID を抽出しのスキーマに準拠したメッセージの構築図形、 **Get_Status**同時実行プログラム。 呼び出すメッセージ、 **Get_Status**同時実行プログラムは、要求 ID をパラメーターとしての Oracle E-business Suite に送信されます。 送信を含めるし、図形、メッセージの構築図形、および Oracle にメッセージを送信し、応答を受信するポートを受信する必要があります。  

 通常、**顧客インターフェイス**同時実行プログラムは、実行する前に待機する必要があるためにを実行するには、しばらく時間がかかります、 **Get_Status**同時実行します。 これを自動化するには追加することで、**遅延**図形。  

 サンプル オーケストレーションには、次のようになります。  

 ![同時実行プログラムを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/2a02e9d8-8ea8-4898-8d05-c060761f4feb.gif "2a02e9d8-8ea8-4898-8d05-c060761f4feb")  

### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 表示される名前、**図形**列は、上記のオーケストレーションに表示されるメッセージの構築図形に対応します。  

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
 場合は、オーケストレーションを呼び出すまでの待機時間を**顧客インターフェイス**と**Get_Status**同時実行のプログラムを追加する必要がある、**遅延**オーケストレーションへの図形。 追加する必要があります、**遅延**図形のオーケストレーションへの応答にコピーした後、**顧客インターフェイス**ファイルへの同時実行プログラムの送信ポート。 そのため、追加する必要があります、**遅延**図形の後に、 **SendResponse**図形。  

 内で、**遅延**図形、時間間隔をオーケストレーションの式エディターに次のコードを追加することで待機を続行する前にする必要がありますを指定することができます、**遅延**図形。  

```  
new System.TimeSpan(0,2,0)  
```  

 このコードを追加すると、オーケストレーションを続行する前に 2 分間待機します。 詳細を構成する方法については、**遅延**図形は、「[遅延図形を構成する方法](../../core/how-to-configure-the-delay-shape.md)します。  

### <a name="adding-the-construct-message-shape"></a>メッセージの構築図形を追加します。  
 Oracle E-business Suite for からの応答、**顧客インターフェイス**同時実行プログラムには、要求 ID が含まれています。 同時実行プログラムのステータスを取得するには、パラメーターとして同じ要求 ID を渡す必要があります、 **Get_Status**同時実行プログラム。 含める必要がありますを行うには、オーケストレーションで、**メッセージの構築**図形、し、その中を**メッセージの割り当て**図形。 目的、**メッセージの構築**図形は。  

- 応答を受信した要求 ID を抽出する、**顧客インターフェイス**同時実行プログラム。  

- メッセージ スキーマに準拠したメッセージを構築する、 **Get_Status**同時実行プログラム。  

  **メッセージの構築**図形は、設定、**メッセージ構築**プロパティを**Get_StatusRequest**します。  

  **メッセージの割り当て**図形を追加の下。 コードを追加する前にいる必要があります。  

```  
XmlDoc = new System.Xml.XmlDocument();  
XmlDoc.LoadXml("<GetStatusForConcurrentProgram xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR'><RequestId /></GetStatusForConcurrentProgram>");  
Get_StatusRequest = XmlDoc;  
Get_StatusRequest.RequestId = xpath(Response,"string(/*[local-name()='RACUSTResponse']/*[local-name()='RACUSTResult']/text())");  
```  

### <a name="adding-ports"></a>ポートの追加  
 ポートを構成するには、次の表の次の論理ポートの各プロパティを指定します。 表示される名前、*ポート*列は、オーケストレーションに表示されるポートの名前に対応します。  

|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*<br />-作成操作*Cust_Interface*します。 この操作のため、**顧客インターフェイス**同時実行プログラム。<br />-作成操作*Get_Status*します。 この操作のため、 **Get_Status**同時実行プログラム。|  
|LOBPort_GetStatus|-設定**識別子**に*LOBPort_GetStatus*<br />-設定**型**に*LOBPort_GetStatusType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表では、メッセージのアクション図形とポートにリンクすることを指定するプロパティ値を指定します。 表示される名前、**図形**列は、オーケストレーション ダイアグラムに表示されるメッセージの構築図形の名前に対応します。  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.Cust_Interface.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBport.Cust_Interface.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBport.Cust_Interface.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.Cust_Interface.Request*|  
|SendGetStatus|-設定**メッセージ**に*Get_StatusRequest*<br />-設定**操作**に*LOBPort_GetStatus.Get_Status.Request*|  
|ReceiveStatusResponse|-設定**メッセージ**に*Get_StatusResponse*<br />-設定**操作**に*LOBPort_GetStatus.Get_Status.Response*|  
|SaveStatusResponse|-設定**メッセージ**に*Get_StatusResponse*<br />-設定**操作**に*ResponseOut.Get_Status.Request*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、次を参照してください。[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)します。  

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**ペインで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 チュートリアルについては、次を参照してください。[チュートリアル。基本的な BizTalk アプリケーション展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)します。  

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle E-business Suite に送信します。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - 2 つの物理 WCF カスタム定義または送信ポートの Wcf-oracleebs: を実行する Oracle E-business Suite にメッセージを送信する 1 つ、**顧客インターフェイス**同時実行プログラムおよび実行する、その他の**Get_Status**同時実行プログラム。 送信ポートでアクションを指定することも必要があります。 ポートを作成する方法については、次を参照してください。 [、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)します。  

     使用して同時実行プログラムを呼び出す、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーションのコンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストのいずれかの操作を指定するには、特定のバインド プロパティを提供します。 同時実行プログラムを起動するために使用する Wcf-custom または Wcf-oracleebs ポートでは、これらのバインド プロパティを設定する必要があります。  

    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**アプリケーションのコンテキストを設定するのには、次のバインド プロパティを指定する必要があります。  


      |        プロパティのバインド         |                                                                                                                                                                                                                                                                                     値                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を含むユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。 |
      |       **OraclePassword**        |   Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にパスワードが渡される\*とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     Oracle E-business Suite ユーザーに関連付けられた役割。                                                                                                                                                                                                                                                      |


    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合、値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  

      異なるバインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

    > [!NOTE]
    >  アプリケーションのコンテキストを設定するには、バインドのプロパティを指定するか、メッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)します。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法については、次を参照してください。 [Oracle E-business Suite でのアプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)します。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、次を参照してください。 [Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)します。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 同時実行プログラムを呼び出す前に、BizTalk アプリケーションを開始する必要があります。 BizTalk アプリケーションを開始する手順については、次を参照してください。[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)します。  

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   Wcf-custom または Wcf-oracleebs 送信ポートを呼び出す、**顧客インターフェイス**同時実行プログラムが実行されています。  

-   Wcf-custom または Wcf-oracleebs 送信ポートを呼び出す、 **Get_Status**同時実行プログラムが実行されています。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 呼び出すためのスキーマに準拠した要求メッセージを削除する必要があります、アプリケーションを実行した後、**顧客インターフェイス**同時実行プログラム。 呼び出す要求のメッセージなど、**顧客インターフェイス**同時実行プログラムは。  

```  
<RACUST xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <Description>Customer Interface Program</Description>  
  <StartTime></StartTime>  
  <CREATE_RECIPROCAL_CUSTOMER>Yes</CREATE_RECIPROCAL_CUSTOMER>  
  <ORG_ID>203</ORG_ID>  
</RACUST>  
```  

> [!NOTE]
>  同時実行プログラムを呼び出すための要求メッセージには、SetOptions、SetPrintOptions、SetRepeatOptions などのいくつかの省略可能なパラメーターが必要です。 ここで指定した要求メッセージでは、これらの省略可能なパラメーターは含まれません。 オプションのパラメーターを含む、完全な要求メッセージに関する情報を参照してください。[同時実行プログラムのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)します。  

 オーケストレーション、メッセージを使用するには、Oracle E-business Suite に渡しますおよび応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 お客様のインターフェイスの同時実行プログラムの応答には、次のようになります。  

```  
<?xml version="1.0" encoding="utf-8"?>  
<RACUSTResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ConcurrentPrograms/AR">  
  <RACUSTResult>2794708</RACUSTResult>  
</RACUSTResponse>  
```  

 Oracle E-business Suite からの応答には、要求 ID が含まれています。 オーケストレーション応答メッセージから要求 ID を抽出し、呼び出すメッセージを構築します、 **Get_Status** 、同時実行プログラムを実行する Oracle E-business Suite に渡す、 **Get_Status**同時実行プログラム。 番目の応答を受信後**Get_Status**同時実行プログラムは、最初の応答として、同じファイルの場所にコピーされます。 応答、 **Get_Status**同時実行プログラムが、次に似ています。  

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
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後、ファイルから構成設定をインポートすると、項目がなどの送信ポートと、同じオーケストレーション用のポートを受信できるように、作成する必要はありません。 バインド ファイルの詳細については、次を参照してください。 [Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)します。  

## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)