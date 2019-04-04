---
title: オーバー ロードされた関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overloaded functions and procedures, invoking by using BizTalk Server
ms.assetid: a3d76361-6b0c-415a-b4f9-31939abfdc36
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2cbe1db96bf6b1c65c77c67c639a3f6ac65a43d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005347"
---
# <a name="invoke-overloaded-functions-and-procedures-in-oracle-database-using-biztalk-server"></a>オーバー ロードされた関数と BizTalk Server を使用して Oracle データベースでプロシージャを呼び出す
Oracle データベースでは、ストアド プロシージャおよび関数をオーバー ロードすることができます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]操作のターゲットの名前空間を変更することでオーバー ロード関数およびプロシージャのサポート。 たとえば、2 つのオーバー ロードされたプロシージャのメッセージの構造は、ようになります。  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
 オーバー ロード関数を呼び出すために必要な SOAP メッセージの構造と SOAP アクションまたは」の説明に従って、プロシージャは、関数およびプロシージャの呼び出しに似て[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)します。  
  
 」の説明に従って、他の関数の呼び出しに似ていますが、オーバー ロードされたプロシージャを呼び出すこと[関数の呼び出しと Oracle データベースを使用して BizTalk Server でプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-biztalk-server.md)します。 ただし、オーバー ロードされた関数を区別するために、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ノード ID とオーバー ロードされた成果物が表示される名前空間に一意の文字列を追加します。 この文字列は、next のオーバー ロードの最初のオーバー ロード"overload2"の"overload1"が。  
  
## <a name="how-to-invoke-overloaded-functions-and-procedures"></a>オーバー ロードされた関数とプロシージャを呼び出す方法は?  
 使用して Oracle データベースでの操作を実行する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で説明されている手順のタスクが含まれます[Oracle データベースと BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)します。 これらのタスクは、Oracle データベースで関数の呼び出しには。  
  
1. BizTalk プロジェクトを作成し、Oracle データベースで、呼び出し先関数のオーバー ロードされたスキーマを生成します。  
  
2. Oracle データベースからメッセージを送受信するための BizTalk プロジェクトでは、メッセージを作成します。 各オーバー ロードのメッセージを作成する必要があります。  
  
3. Oracle データベースでオーバー ロードされた関数を呼び出すオーケストレーションを作成します。  
  
4. ビルドし、BizTalk プロジェクトを配置します。  
  
5. BizTalk 物理を作成してアプリケーションの送信および受信ポートを構成します。  
  
6. BizTalk アプリケーションを起動します。  
  
   このトピックでは、これらのタスクを実行する手順を説明します。  
  
## <a name="sample-based-on-this-topic"></a>このトピックに基づくサンプル  
 サンプル InvokeOverloadedProc、このトピックの「に基づいてが付属しても、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  
  
## <a name="generating-schema"></a>スキーマを生成します。  
 このトピックで、オーバー ロードされた関数またはプロシージャを呼び出す方法を示すために私たちは、GET_ACCOUNT プロシージャを呼び出す SCOTT\Package\ACCOUNT_PKG スキーマの下。 このパッケージは、サンプルで提供される SQL スクリプトを実行して、SCOTT スキーマの下に作成されます。 これは、オーバー ロードされたプロシージャ場所。  
  
- 1 つのオーバー ロードは、IN パラメーターとしてアカウント ID を受け取り、出力パラメーターとして、アカウント %rowtype を返します。  
  
- 2 番目のオーバー ロードは、IN パラメーターとして、アカウント名を受け取り、出力パラメーターとして、アカウント %rowtype を返します。  
  
  サンプルとの SQL スクリプトの詳細については、[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)を参照してください。  
  
  オーバー ロード関数を呼び出すため、両方のオーバー ロードされたプロシージャ、GET_ACCOUNT.1 と GET_ACCOUNT.2 のスキーマを生成します。 参照してください[Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)スキーマを生成する方法の詳細について。  
  
## <a name="defining-messages-and-message-types"></a>メッセージおよびメッセージの種類を定義します。  
 以前に生成したスキーマには、オーケストレーション内のメッセージに必要な「型」について説明します。 メッセージは、通常、対象の型が、対応するスキーマで定義されている、変数です。 BizTalk プロジェクトのオーケストレーションの種類 ウィンドウからのメッセージを最初の手順で生成したスキーマをリンクする必要があります。  
  
 このトピックでは、2 つの要求-応答メッセージのセットを作成する必要があります: 2 つ目のオーバー ロードされたプロシージャの設定の最初の手順と、2 番目の要求-応答をオーバー ロードの 1 つの要求-応答を設定します。  
  
 メッセージを作成し、スキーマにリンクするには、次の手順を実行します。  
  
#### <a name="to-create-messages-and-link-to-schema"></a>メッセージを作成し、スキーマにリンクするには  
  
1.  開いていない場合は、BizTalk プロジェクトのオーケストレーションの種類 ウィンドウを開きます。 これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。  
  
2.  オーケストレーション ビューで右クリックして**メッセージ**、 をクリックし、**新しいメッセージ**します。  
  
3.  新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。  
  
4.  **プロパティ**ウィンドウ **[message_1]** 次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[Identifier]|型**要求**します。|  
    |メッセージ型|ドロップダウン リストから展開**スキーマ**、選択と*InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNT*ここで、 *InvokeOverloadedProc*の名前を指定します。BizTalk プロジェクト。 *OracleDBBindingSchema* GET_ACCOUNT プロシージャに対して生成されるスキーマです。|  
  
5.  次の 3 つ以上のメッセージを作成する前の手順を繰り返します。 **プロパティ**ウィンドウで、新しいメッセージの場合は、次を実行します。  
  
    |識別子を設定するには|メッセージの種類を設定|  
    |-----------------------|-------------------------|  
    |応答|*InvokeOverloadedProc.OracleDBBindingSchema.GET_ACCOUNTResponse*|  
    |Request2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNT*|  
    |Response2|*InvokeOverloadedProc.OracleDBBindingSchema1.GET_ACCOUNTResponse*|  
  
## <a name="setting-up-the-orchestration"></a>オーケストレーションのセットアップ  
 使用する BizTalk オーケストレーションを作成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Oracle データベース内のオーバー ロードされたプロシージャを呼び出すためです。 このオーケストレーションで 2 つの要求メッセージを削除する、定義済みの各オーバー ロードされたプロシージャに対応する 1 つの受信場所。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージを使用し、ODP を使用して Oracle データベースに渡します。 Oracle データベースからの応答は、別の場所に保存されます。  
  
 オーケストレーションでは、同時に 2 つの要求が取得するために並列アクション図形をオーケストレーションに含める必要があります。 並列アクションごとは、送信が含まれます、受信図形、Oracle データベースにメッセージを送信し、応答を受信する必要があります。 ただし、両方の操作のメッセージを送受信するため、同じポートを使用できます。 同時にオーバー ロードされたプロシージャを呼び出すための一般的なオーケストレーションが含まれます。  
  
- Oracle データベースにメッセージを送信し、応答を受信する図形を送受信します。  
  
- Oracle データベースに送信する要求メッセージを受信するポートは一方向の受信します。  
  
- 双方向の送信要求メッセージを Oracle データベースし、応答の受信を送信するポート。  
  
- フォルダーに Oracle データベースからの応答を送信する一方向の送信ポート。  
  
  サンプル オーケストレーションを GET_ACCOUNT プロシージャの最初と 2 番目のオーバー ロードを呼び出すには、次のようになります。  
  
  ![オーバー ロードされたパッケージを呼び出すためのオーケストレーション](../../adapters-and-accelerators/adapter-oracle-database/media/f8e4ad6f-9140-43b1-b931-28c9ba11cc8e.gif "f8e4ad6f-9140-43b1-b931-28c9ba11cc8e")  
  
### <a name="adding-message-shapes"></a>メッセージの構築図形を追加します。  
 メッセージの構築図形のごとに、次のプロパティを指定することを確認します。 図形の列に示した名前は、単に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。 次の表は、図形の並列アクションの 1 つ含める必要があります。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-設定**名前**に*ReceiveMessage*<br />-設定**アクティブ**に*は True。*|  
|SendMessage|Send|-設定**名前**に*SendMessage*|  
|ReceiveResponse|Receive|-設定**名前**に*ReceiveResponse*<br />-設定**アクティブ**に*False*|  
|SendResponse|Send|-設定**名前**に*SendResponse*|  
  
 次の表では、その他の並列アクションを含める必要のある図形が一覧表示します。  
  
|図形|図形の種類|[プロパティ]|  
|-----------|----------------|----------------|  
|ReceiveMessage2|Receive|-設定**名前**に*ReceiveMessage2*<br />-設定**アクティブ**に*は True。*|  
|SendMessage2|Send|-設定**名前**に*SendMessage2*|  
|ReceiveResponse2|Receive|-設定**名前**に*ReceiveResponse2*<br />-設定**アクティブ**に*False*|  
|SendResponse2|Send|-設定**名前**に*SendResponse2*|  
  
### <a name="adding-ports"></a>ポートの追加  
 論理ポートごとに、次のプロパティを指定することを確認します。 ポート列に示した名前は、オーケストレーションで表示されているポートの名前です。  
  
|Port|[プロパティ]|  
|----------|----------------|  
|FileIn|-設定**識別子**に*FileIn*<br />-設定**型**に*FileInType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*受信*|  
|LOBPort|-設定**識別子**に*LOBPort*<br />-設定**型**に*LOBPortType*<br />-設定**通信パターン**に*要求-応答*<br />-設定**通信方向**に*送受信*|  
|SaveResponse|-設定**識別子**に*SaveResponse*<br />-設定**型**に*SaveResponseType*<br />-設定**通信パターン**に*一方向*<br />-設定**通信方向**に*送信*|  
  
 2 つの要求を処理するため、これらのポートを使用して応答メッセージは、ポートごとに各操作が 1 つのメッセージの種類に対応する 2 つの操作を作成する必要があります。 操作を作成するポート図形を右クリックし、**新しい操作**します。 最初の操作としては、各ポートの名前を付けます**Overload1**としてポートごとに 2 番目の操作と**Overload2**します。  
  
### <a name="using-correlation"></a>相関関係の使用  
 関連付けは、受信メッセージをオーケストレーションの適切なインスタンスに一致させるプロセスです。 削除するオーケストレーションに 2 つの要求メッセージは、各オーバー ロードのいずれか。 相関関係を使用して、適切なオーケストレーションを要求メッセージに関連付けます。 相関関係の詳細については、[オーケストレーションでの相関関係を使用して](../../core/using-correlations-in-orchestrations.md)を参照してください。  
  
##### <a name="to-use-correlations"></a>相関関係を使用するには  
  
1.  各オーバー ロードされた関数の生成スキーマからプロパティを昇格します。 たとえば、最初のオーバー ロードのスキーマから支援プロパティを昇格させます2 番目のオーバー ロードのスキーマから ANAME プロパティを昇格させます。 プロパティを昇格させるには、スキーマ ビューでプロパティを右クリックして**昇格**、し、**クイック昇格**します。 これにより、PropertySchema.xsd ファイルが BizTalk プロジェクトに追加します。  
  
     プロパティを昇格する方法の詳細については、[プロパティの昇格](../../core/promoting-properties.md)を参照してください。  
  
2.  オーケストレーションの種類を右クリックして**関連付けの種類**、し、**新しい関連付けの種類**します。  
  
3.  **関連付けのプロパティ** ダイアログ ボックスには、手順 1. で昇格させたプロパティが一覧表示されます。 プロパティを選択し、**追加**します。  
  
4.  **[OK]** をクリックします。  
  
5.  その他の昇格させたプロパティの関連付けの種類を作成するには、この手順を繰り返します。  
  
6.  関連付けられているプロパティに基づいて関連付けの種類の名前を変更します。 関連付けの種類の名前を変更することが*CorrelationType_AID* (補助プロパティ) 用と*CorrelationType_ANAME* (ANAME プロパティ) 用。  
  
7.  オーケストレーションの種類を右クリックして**関連付けセット**、し、**新しい関連付けセット**します。  
  
8.  新しく追加された関連付けセットを右クリックし、をクリックし、**プロパティ**します。 プロパティ ペインで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*InvokeOverloadedProc.CorrelationType_AID*|  
    |[Identifier]|*Correlation_AID*|  
  
9. 別の関連付けセットを追加し、[プロパティ] ウィンドウから次のプロパティを指定します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |[関連付けの種類]|*InvokeOverloadedProc.CorrelationType_ANAME*|  
    |[Identifier]|*Correlation_ANAME*|  
  
## <a name="specify-messages-for-action-shapes-and-connect-them-to-ports"></a>アクション図形は、メッセージを指定し、ポートに接続  
 次の表では、プロパティとアクション図形のメッセージを指定して、メッセージ ポートにリンクを設定する必要があります、値を指定します。 図形の列に示した名前は、前に説明したオーケストレーションに表示されるメッセージの構築図形の名前です。  
  
|図形|[プロパティ]|  
|-----------|----------------|  
|ReceiveMessage|-設定**イニシャライズ関連付けセット**に*Correlation_AID*<br />-設定**メッセージ**に*要求*<br />-設定**操作**に*FileIn.Overload1.Request*|  
|SendMessage|-設定**メッセージ**に*要求*<br />-設定**操作**に*LOBPort.Overload1.Request*|  
|ReceiveResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*LOBPort.Overload1.Response*|  
|SendResponse|-設定**メッセージ**に*応答*<br />-設定**操作**に*SaveResponse.Overload1.Request*|  
|ReceiveMessage2|-設定**イニシャライズ関連付けセット**に*Correlation_ANAME*<br />-設定**メッセージ**に*Request2*<br />-設定**操作**に*FileIn.Overload2.Request*|  
|SendMessage2|-設定**メッセージ**に*Request2*<br />-設定**操作**に*LOBPort.Overload2.Request*|  
|ReceiveResponse2|-設定**メッセージ**に*Response2*<br />-設定**操作**に*LOBPort.Overload2.Response*|  
|SendResponse2|-設定**メッセージ**に*Response2*<br />-設定**操作**に*SaveResponse.Overload2.Request*|  
  
 これらのプロパティを指定したら、メッセージの構築図形とポートが接続されているし、オーケストレーションが完了します。  
  
 ここで、BizTalk ソリューションをビルドしに配置する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 詳細については、[を実行しているオーケストレーションのビルドと](../../core/building-and-running-orchestrations.md)を参照してください。  
  
## <a name="configuring-the-biztalk-application"></a>BizTalk アプリケーションを構成します。  
 先ほど作成したオーケストレーションが 下にある BizTalk プロジェクトを配置した後、**オーケストレーション**BizTalk Server 管理コンソール ウィンドウ。 BizTalk Server 管理コンソールを使用して、アプリケーションを構成する必要があります。 チュートリアルについては、[チュートリアル: 基本的な BizTalk アプリケーションの展開](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md)を参照してください。
  
 アプリケーションを構成する必要があります。  
  
- アプリケーションのホストを選択します。  
  
- BizTalk Server 管理コンソールで物理ポートにオーケストレーションで作成したポートをマッピングします。 このオーケストレーションの次の操作を行う必要があります。  
  
  - ハード ディスクと、各オーバー ロードされたプロシージャの 1 つの要求メッセージをドロップする場所、対応するファイル ポートでの場所を定義します。 BizTalk オーケストレーションは要求メッセージを使用して、Oracle データベースに送信します。  
  
  - ハード ディスクと、BizTalk オーケストレーションが応答メッセージは、Oracle データベースからの応答を含む、各オーバー ロードされたプロシージャのいずれかをドロップする場所、対応するファイル ポートでの場所を定義します。  
  
  - Oracle データベースにメッセージを送信する物理 Wcf-custom または Wcf-oracledb 送信ポートを定義します。 送信ポートでアクションを指定することも必要があります。 Wcf-custom または Wcf-oracledb のポートを作成する方法については、[、Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)を参照してください。 Wcf-custom または Wcf-oracledb 送信ポートは 1 つ以上のスキーマに準拠したメッセージの送受信および 2 つの操作を実行、ためには、両方の操作のための動的アクションを設定する必要があります。 アクションの詳細については、[Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)を参照してください。 このオーケストレーションでは、アクションをよう設定する必要があります。  
  
    ```  
    <BtsActionMapping>  
      <Operation Name="Overload1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1" />  
      <Operation Name="Overload2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2" />  
    </BtsActionMapping>  
    ```  
  
    > [!NOTE]
    >  使用して、スキーマの生成、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートとそれらのポートに設定するアクションに関する情報を含むバインド ファイルも作成されます。 (発信) の送信ポートを作成または (着信) 用のポートを受信する BizTalk Server 管理コンソールから、このバインド ファイルをインポートできます。 詳細については、[Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)を参照してください。  
  
## <a name="starting-the-application"></a>アプリケーションの起動  
 Oracle のデータベース テーブル内の関数を呼び出す BizTalk アプリケーションを起動する必要があります。 BizTalk アプリケーションを開始する手順については、[オーケストレーションを開始する方法](../../core/how-to-start-an-orchestration.md)を参照してください。  
  
 この段階で、ことを確認します。  
  
-   ファイルは、オーケストレーションが実行中の要求メッセージを受信するポートを受信します。  
  
-   オーケストレーションから応答メッセージを受信する FILE 送信ポートが実行されています。  
  
-   Oracle データベースにメッセージを送信する Wcf-custom または Wcf-oracledb の送信ポートが実行されています。  
  
-   操作の BizTalk オーケストレーションが実行されています。  
  
## <a name="executing-the-operation"></a>操作の実行  
 アプリケーションを実行した後、2 つを削除する必要がありますファイルへのメッセージ (各オーバー ロードされたプロシージャの 1 つ) の受信場所を要求します。 要求メッセージのスキーマは、以前に作成したプロシージャのスキーマに準拠する必要があります。 参照してください[関数およびプロシージャのメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)を使用する関数を呼び出すための要求メッセージ スキーマの詳細について、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
 たとえば、GET_ACCOUNT プロシージャの最初のオーバー ロードを呼び出す要求メッセージには。  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
  <AID>100001</AID>  
</GET_ACCOUNT>  
```  
  
 同様に、GET_ACCOUNT プロシージャの 2 番目のオーバー ロードを呼び出す要求メッセージは次のとおりです。  
  
```  
<GET_ACCOUNT xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload2">  
  <ANAME>Mindy Martin</ANAME>  
</GET_ACCOUNT>  
```  
  
 最初の要求メッセージは、100020 と等しいアカウント ID を持つレコードを取得する GET_ACCOUNT プロシージャを呼び出します。 2 番目の要求メッセージは、"John Smith"とアカウントの名前を持つレコードを取得する GET_ACCOUNT プロシージャを呼び出します。  
  
 オーケストレーションでは、要求メッセージを使用し、Oracle データベースに送信します。 Oracle データベースからの応答は、オーケストレーションの一部として定義されているその他のファイルの場所に保存されます。 たとえば、最初のオーバー ロードされたプロシージャ呼び出しの応答には。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<GET_ACCOUNTResponse mlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT/overload1">  
 <ACCT>  
  <ACCTID>100001</ACCTID>  
  <NAME>Ty Carlson</NAME>  
  <BALANCE>9000</BALANCE>  
 </ACCT>  
</GET_ACCOUNTResponse>  
```  
  
## <a name="possible-exceptions"></a>可能性のある例外  
 例外に関する情報を使用するオーバー ロードされたパッケージの呼び出し中に発生する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[例外とエラー処理](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)します。  
  
## <a name="best-practices"></a>ベスト プラクティス  
 展開し、BizTalk プロジェクトの構成後は、バインド ファイルと呼ばれる XML ファイル構成設定をエクスポートできます。 バインド ファイルを生成した後は、受信ポートなど、同じオーケストレーションの送信ポートを作成する必要はありませんように、ファイルから構成設定をインポートできます。 バインド ファイルの詳細については、[Oracle データベース アダプターの再利用バインド](../../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)を参照してください。  
  
## <a name="see-also"></a>参照  
[Oracle Database による開発の BizTalk アプリケーションを構成要素](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)