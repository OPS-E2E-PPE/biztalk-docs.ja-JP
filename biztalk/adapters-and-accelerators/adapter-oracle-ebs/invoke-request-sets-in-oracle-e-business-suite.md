---
title: Oracle E-business Suite での要求のセットを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a79bff63-325d-4745-ab0e-839e00476ab1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da52668f0e94da23afdd8246f0acb0ca89d1c36a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014123"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite"></a>Oracle E-business Suite での要求のセットを呼び出す
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite での要求セットを実行できます。 要求セットは 1 つまたは複数の段階に分けられ、各ステージには、一連レポートと同時実行プログラムにはが含まれています。 します。 アダプターが要求のセットをサポートする方法の詳細については、[に対する要求の設定操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)を参照してください。 要求セットを呼び出すためのメッセージを SOAP の構造についてを参照してください。[要求の設定のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)します。  

## <a name="prerequisites"></a>前提条件  
 」の手順を完了する必要があります[Oracle E-business Suite のアプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-oracle-ebs/prerequisites-to-create-oracle-e-business-suite-applications.md)します。  

## <a name="how-to-invoke-request-sets-in-oracle-e-business-suite"></a>Oracle E-business Suite で要求を呼び出す方法の設定します。  
 Oracle E-business Suite を使用して、操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle E-business Suite のアプリケーションを作成する構成要素](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)します。 要求を呼び出すには、これらのタスクは。  

- BizTalk プロジェクトを作成し、呼び出し先要求セットのスキーマを生成します。  

- Oracle E-business Suite からの送信とメッセージの送受信用の BizTalk プロジェクトでは、メッセージを作成します。  

- 要求のセットを呼び出すオーケストレーションを作成します。  

- ビルドし、BizTalk プロジェクトを配置します。  

- BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  

- BizTalk アプリケーションを起動します。  

  このトピックでは、これらのタスクを実行する手順を説明します。  

## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックでは、呼び出すことによって、要求のセットを呼び出す方法を示します、**関数のセキュリティ レポート**(表示名) 要求の設定から、**アプリケーション オブジェクト ライブラリ**アプリケーション。 実際の要求セットの名前は**FNDRSSUB43**します。 この要求のセットは、既定の Oracle E-business Suite アプリケーションで使用できます。 この要求のセットは、要求 ID を返します  

 スキーマを生成このトピックでは、そのため、 **FNDRSSUB43**セットを要求します。 参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  

## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 先に生成したスキーマは、オーケストレーションのメッセージに求められる "型" を記述します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 オーケストレーションでは、メッセージを作成し、前の手順で生成したスキーマにリンクする必要がありますようになりました。  

 このオーケストレーションでは、2 つのメッセージを作成する必要があります: 1 つを呼び出す要求セットと、要求のセットに対する応答を受信するメッセージを送信します。  

#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  

1.  オーケストレーションを BizTalk プロジェクトに追加します。 ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。 BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。  

2.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  

3.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  

4.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  

5.  **プロパティ**のウィンドウ、 **Message_1**次の操作を行います。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|「`Request`」と入力します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、し、 *RequestSet.OracleEBSBindingRequestSets_FND します。FNDRSSUB43*RequestSet は、BizTalk プロジェクトの名前です。 OracleEBSBindingRequestSets が呼び出すために生成されたスキーマ、 **FNDRSSUB43**セットを要求します。|  

6.  手順 3 メッセージを作成する. **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  

    |プロパティ|目的|  
    |--------------|----------------|  
    |応答|*RequestSet.OracleEBSBindingRequestSets_FND します。FNDRSSUB43Response*|  

## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle E-business Suite での要求のセットを呼び出すためです。 要求メッセージをこのオーケストレーションで削除する、定義されている受信場所。 オーケストレーションがこのメッセージを使用し、それを呼び出すための Oracle E-business Suite に渡します、 **FNDRSSUB43**セットを要求します。 要求セットの応答は、Oracle から受信され、別の場所に保存されます。 要求のセットを呼び出すための一般的なオーケストレーションが含まれます。  

- Oracle E-business Suite にメッセージを送信し、応答を受信する図形を送受信します。  

- Oracle E-business Suite に送信する要求メッセージを受信するポートは一方向の受信します。  

- Oracle E-business Suite に要求メッセージを送信し、応答を受信するポートを双方向に送信します。  

- Oracle E-business Suite からフォルダーに、応答を送信する一方向の送信ポート。  

  要求のセットを起動するサンプル オーケストレーションには、次のようになります。  

  ![要求セットを呼び出すオーケストレーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ea161292-8613-4c0b-ac24-2f26c54bf3a3.gif "ea161292-8613-4c0b-ac24-2f26c54bf3a3")  

### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 各メッセージの構築図形の次のプロパティを指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  

|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  

### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 表示される名前、*ポート*列は、ポートの名前、オーケストレーションに表示されます。  

|Port|[プロパティ]|  
|----------|----------------|  
|MessageIn|-設定**識別子**に*MessageIn*<br />-設定**型**に*MessageInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|ResponseOut|-設定**識別子**に*ResponseOut*<br />-設定**型**に*ResponseOutType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>アクション図形のメッセージを指定し、ポートに接続  
 次の表には、プロパティとメッセージのアクション図形とポートにリンクすることを指定するために設定するには、その値を指定します。 表示される名前、*図形*前のオーケストレーションに表示される、列は、メッセージの構築図形の名前。  

|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*MessageIn.RequestSet.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.RequestSet.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.RequestSet.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*ResponseOut.RequestSet.Request*|  

 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  

 BizTalk ソリューションを構築するようになりましたし、BizTalk Server にデプロイする必要があります。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。  

## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 [オーケストレーション] ペインで先ほど作成したオーケストレーションが表示されている BizTalk プロジェクトを配置した後、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールにアプリケーションを構成します。 アプリケーションを構成する方法の詳細については、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。  

 アプリケーションを構成する必要があります。  

- アプリケーションのホストを選択します。  

- 物理ポートにオーケストレーションで作成したポートのマッピング、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 このオーケストレーションの次の操作を行う必要があります。  

  - ハード ディスクと、要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用し、Oracle E-business Suite に送信します。  

  - ハード ディスクと、対応するファイル ポートを BizTalk オーケストレーションが Oracle E-business Suite からの応答を含む応答メッセージをドロップする場所の場所を定義します。  

  - Oracle E-business Suite にメッセージを送信する物理 Wcf-custom または Wcf-oracleebs 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 送信ポートを作成する方法については、[、Oracle E-business アダプターを物理ポート バインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)を参照してください。  

     要求を呼び出すための設定を使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]操作が呼び出される適切なアプリケーションのコンテキストを設定する必要があります。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーション コンテキストのいずれかの操作を指定するには、特定のバインド プロパティを提供します。 要求セットを呼び出すために使用する Wcf-custom または Wcf-oracleebs ポートでは、これらのバインドのプロパティを設定する必要があります。  

    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**データベース**アプリケーションのコンテキストを設定するのには、次のバインド プロパティを指定する必要があります。  


      |        プロパティのバインド         |                                                                                                                                                                                                                                                                                     値                                                                                                                                                                                                                                                                                     |
      |---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |       **OracleUserName**        | Oracle E-business Suite ユーザーの名前を指定します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OracleUserName** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にユーザー名が渡される\*とします。 ただし、保持するユーザー名の大文字と小文字の場合、または特殊文字を含むユーザー名を入力する場合は、二重引用符で囲まれた値を指定する必要があります。 |
      |       **OraclePassword**        |   Oracle E-business Suite ユーザーのパスワード。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用に入力した値の大文字と小文字は保持されません、 **OraclePassword** Oracle E-business Suite への接続時にプロパティをバインドします。 SQL の標準の規則を使用して Oracle E-business Suite にパスワードが渡される\*とします。 ただし、保持するパスワードの大文字と小文字の場合、または特殊文字を含むパスワードを入力する場合は、二重引用符で囲まれた値を指定する必要があります。    |
      | **OracleEBSResponsibilityName** |                                                                                                                                                                                                                                                     Oracle E-business Suite ユーザーに関連付けられた役割。                                                                                                                                                                                                                                                      |


    - 場合、 **ClientCredentialType**に設定されているプロパティのバインド**EBusiness**、する必要がありますを指定していない Oracle E-business 資格情報の接続を確立中にします。 このような場合、値を指定する必要がありますのみ、 **OracleEBSResponsibilityName**プロパティをバインドします。  

      異なるバインディング プロパティの詳細については、[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 アダプターがアプリケーションのコンテキストの設定がサポートする方法の詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

    > [!NOTE]
    >  アプリケーションのコンテキストを設定するには、バインドのプロパティを指定するか、メッセージによって公開されるコンテキスト プロパティを設定して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 バインドのプロパティを設定する方法については、[Oracle E-business suite バインド プロパティの構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)を参照してください。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定する方法については、[Oracle E-business Suite でのアプリケーション コンテキストを使用してメッセージのコンテキスト プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-application-context-using-message-context-properties-in-oracle-ebs.md)を参照してください。  
    > 
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 このバインド ファイルをインポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール (発信) の送信ポートを作成したり (着信) 用のポートを受信します。 詳細については、[Oracle E-business Suite へのポートのバインド ファイルを物理ポートのバインドを使用して、を構成](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  

## <a name="starting-the-application"></a>アプリケーションの起動  
 要求のセットを呼び出すための BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。  

 この段階で、ことを確認します。  

-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  

-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  

-   Wcf-custom または Wcf-oracleebs 送信ポートを呼び出す、 **FNDRSSUB43**要求セットが実行されています。  

-   操作の BizTalk オーケストレーションが実行されています。  

## <a name="executing-the-operation"></a>操作の実行  
 呼び出すためのスキーマに準拠した要求メッセージを削除する必要があります、アプリケーションを実行した後、 **FNDRSSUB43**セットを要求します。 呼び出す要求のメッセージなど、 **FNDRSSUB43**要求セットには。  

```  
<FNDRSSUB43 xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <StartTime></ StartTime>  
  <All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
    <FNDMNNAV xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNNAV>  
    <ns2:FNDMNMNU xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNMNU>  
    <ns2:FNDMNFUN xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetStage/FND/FNDRSSUB43">  
      <ns3:Responsibility xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND">System Administrator</ns3:Responsibility>  
      <ns3:Application xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSetConcurrentProgram/FND/FNDRSSUB43/STAGE10/FND"></ns3:Application>  
    </ns2:FNDMNFUN>  
  </ns0:All_x0020_Requests_x0020_in_x0020_the_x0020_Set_STAGE10>  
</ns0:FNDRSSUB43>  
```  

> [!NOTE]
>  要求のセットを呼び出すための要求メッセージには、SetRelClassOptions、SetPrintOptions、SetRepeatOptions、SetNlsOptions などのいくつかの省略可能なパラメーターが必要です。 ここで指定した要求メッセージでは、これらの省略可能なパラメーターは含まれません。 オプションのパラメーターを含む、完全な要求メッセージに関する情報を参照してください。[要求セットのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)します。  

 オーケストレーション、メッセージを使用するには、Oracle E-business Suite に渡しますおよび応答を受信します。 応答メッセージは、オーケストレーションの一部として指定されたその他のファイルの場所に保存されます。 応答、 **FNDRSSUB43**セット、次のよう要求。  

```  
<?xml version="1.0" encoding="utf-8"?>  
<FNDRSSUB43Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/RequestSets/FND">  
  <FNDRSSUB43Result>2543208</FNDRSSUB43Result>  
</FNDRSSUB43Response>  
```  

 Oracle E-business Suite からの応答には、要求 ID が含まれています。 要求があることを示します ID '0'、最後の送信が失敗した要求の操作。 このような場合は、要求などのメッセージ、ContinueOnFail、失敗の理由を確認して、さらにデバッグで省略可能なその他のパラメーターを指定できます。  

## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した、送信ポートなどの項目を作成し、同じオーケストレーション用のポートを受信する必要はありませんように構成設定、ファイルからインポートできます。 バインド ファイルの詳細については、[Oracle E-business suite アダプターのバインドを再利用](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)を参照してください。  

## <a name="see-also"></a>参照  
[Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。 ](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)