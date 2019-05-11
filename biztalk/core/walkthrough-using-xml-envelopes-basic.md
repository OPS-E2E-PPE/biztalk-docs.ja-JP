---
title: 'チュートリアル: XML エンベロープ (Basic) の使用 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- content-based routing, promoting properties
- promoting properties, routing messages
- promoting properties, content-based routing
- routing, messages
- routing, promoting properties
ms.assetid: 02d0c596-0cfe-4bae-9f1b-d7dbc17e18a9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f614a1400631a1bae36a1f15dc4b1f6916b45916
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279635"
---
# <a name="walkthrough-using-xml-envelopes-basic"></a>チュートリアル: XML エンベロープ (Basic) の使用
この例では、架空のエラー追跡システムを実装して、基本的な XML エンベロープの逆アセンブルを示します。 この例は次の要件を満たしています。  
  
1.  エラー メッセージは社内のさまざまな物理的な場所でログに記録され、集中管理された場所に送信されて、さまざまなバックエンド システムに振り分けられます。  
  
2.  エラー メッセージは XML 形式で書き込まれます。  
  
3.  エラー メッセージは、エンベロープなしで単独に送信したり、エンベロープに含まれるバッチとして送信したりできます。  
  
## <a name="prerequisites"></a>前提条件  
 この例では、BizTalk プロジェクトの作成、アセンブリへの署名、BizTalk Server 管理コンソールでのアプリケーションとポートの表示に慣れている必要があります。 またはずで紹介したアイデアに[チュートリアル。基本的な BizTalk アプリケーション展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。  
  
## <a name="what-this-example-does"></a>この例の処理  
 この例では、エンベロープ スキーマを定義し、XmlDisassembler パイプラインを使用して、単一のエラー メッセージまたはエラー メッセージのバッチを含む受信メッセージを処理します。  
  
## <a name="example"></a>例  
 この例を作成するには、以下で概要を説明している手順を実行します。  
  
### <a name="create-a-new-biztalk-project"></a>新しい BizTalk プロジェクトの作成  
 BizTalk プロジェクトを作成する必要があるソリューションをビルドする前に、ソリューションに厳密な名前が付いていることを確認し、アプリケーション名をそのソリューションに割り当てます。 アプリケーション名を割り当てると、そのソリューションが BizTalk Server によって既定の BizTalk アプリケーションに配置されるのを防ぐことができます。  
  
##### <a name="to-create-and-configure-a-new-biztalk-project"></a>新しい BizTalk プロジェクトを作成および構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して新しい BizTalk プロジェクトを作成します。 プロジェクトを呼び出す**BasicXMLEnvelope**します。  
  
2. キー ファイルを作成してプロジェクトに割り当てます。 このタスクの詳細については、次を参照してください。[厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)します。  
  
3. プロジェクトの配置構成プロパティを割り当てて、**アプリケーション名**設定と**ホスト インスタンスを再起動**に`True`します。 このフラグを設定すると、キャッシュされたアセンブリのインスタンスを消去するようにホストに通知されます。  
  
### <a name="create-the-error-schema"></a>エラー スキーマの作成  
 このステップではエラー スキーマを作成します。 システムのキー メッセージを定義します。  
  
##### <a name="to-create-the-error-schema"></a>エラー スキーマを作成するには  
  
1. プロジェクトに "エラー" という名前の新しいスキーマを追加します。  
  
2. 変更するスキーマのターゲットの名前空間 **http://BasicXMLEnvelope**します。  
  
3. スキーマ プロパティを変更**Element FormDefault**下、 **[詳細設定]** カテゴリ**Qualified**します。 これは、ローカルに宣言された要素を、ターゲットの名前空間を使用してインスタンス ドキュメント内で修飾する必要があることを示します。  
  
4. ルート ノードの名前を "エラー" に変更し、次に示す型の 5 つの子要素を作成します。  
  
   - ID、xs:int 型  
  
   - Type、xs:int 型  
  
   - Priority、xs:string 型  
  
   - Description、xs:string 型  
  
   - ErrorDateTime、xs:string 型  
  
     スキーマは以下のようになります。  
  
     ![完成したエラー スキーマ](../core/media/error-schema.gif "error_schema")  
  
5. このスキーマに対応するサンプル メッセージを作成します。 このメッセージは、エンベロープの外部の単一メッセージが適切に処理されているかどうかを確認するために使用します。 以下に、サンプル メッセージの例を示します。  
  
   ```  
   <Error xmlns="http://BasicXMLEnvelope">  
     <ID>1</ID>  
     <Type>5</Type>  
     <Priority>Low</Priority>  
     <Description>Sprocket widget prints reports slowly.</Description>  
     <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
   </Error>  
   ```  
  
    このメッセージをプロジェクト ディレクトリ内のファイルに保存します。  
  
### <a name="create-the-envelope-schema"></a>エンベロープ スキーマの作成  
 エンベロープには、1 つ以上のエラー メッセージが格納されます。 この基本の例のエンベロープには、独自のプロパティおよび要素がありません。  
  
##### <a name="to-create-the-envelope-schema"></a>エンベロープ スキーマを作成するには  
  
1.  BasicXMLEnvelope プロジェクトに "エンベロープ" という名前の新しいスキーマを追加します。  
  
2.  ターゲット名前空間を変更 **http://BasicXMLEnvelope**します。  
  
3.  ルート ノードの名前を "ルート" から "エンベロープ" に変更します。  
  
4.  次に、スキーマをエンベロープ スキーマとしてマークします。 をクリックして、 **\<スキーマ\>** ノード。 プロパティ ペインで、スキーマ参照プロパティを設定**エンベロープ**に`OK`します。  
  
5.  設定、**ボディ XPath**プロパティ。 これを行うには、クリックして、**エンベロープ**ノード。 [プロパティ] ウィンドウで、省略記号ボタンをクリックします (**...**) ボタン、**ボディ XPath**プロパティで、**エンベロープ**、順にクリックします**OK**します。  
  
6.  [エンベロープ] ノードにすべての子要素を追加します。 この要素にエラー メッセージが含まれます。 スキーマは以下のようになります。  
  
     ![完成したエンベロープ スキーマ](../core/media/envelope-schema.gif "envelope_schema")  
  
7.  エンベロープと 1 つ以上のサンプル メッセージを含むサンプル メッセージを作成します。 以下に、メッセージの例を示します。  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error>  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
     このメッセージをプロジェクト ディレクトリ内のファイルに保存します。  
  
### <a name="deploy-and-configure-the-send-and-receive-ports"></a>受信ポートと送信ポートの配置および構成  
 スキーマを作成したら、次はプロジェクトをコンパイルして配置する必要があります。 プロジェクトを配置すると、BizTalk Server 管理コンソールを使用して、送信ポートと受信ポートを構成できます。  
  
##### <a name="to-deploy-basicxmlenvelope"></a>BasicXMLEnvelope を配置するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、選択 **[BasicXMLEnvelope の配置**ビルド] メニューから。 この操作により、BizTalk Server に "BasicXMLEnvelope" アプリケーションとしてビルドおよび配置されます。  
  
2. BizTalk Server 管理コンソールで、**アプリケーション**ことを確認するグループ **[basicxmlenvelope]** がカスタム アプリケーションとして存在します。  
  
##### <a name="to-configure-the-receive-port"></a>受信ポートを構成するには  
  
1.  下の"Receive"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **basicxmlenvelope**アプリケーションを右クリックして**受信ポート**、 をポイント**新規**順にクリックします**一方向受信ポート**します。  
  
3.  **受信ポートのプロパティ** ダイアログ ボックスで、ポートを"Receive"の名前を設定します。  
  
4.  受信場所を右クリックし、をクリックし、**新規**受信ポートを追加します。 新しいポートに "ReceiveError" という名前を付けます。 設定、**受信パイプライン**に**XMLReceive**します。 **トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。  
  
5.  上記で作成した受信ディレクトリを選択し、クリックして**OK**します。 受信ポートが正しく構成されます。 クリックして**OK**を閉じます。  
  
##### <a name="to-configure-the-send-port"></a>送信ポートを構成するには  
  
1.  下の"Send"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、「送信」をポートの名前を設定します。  
  
4.  **トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。 先ほど作成した送信ディレクトリにコピー先のフォルダーを設定し、クリックして**OK**します。  
  
5.  クリックして**フィルター**し、1 つのフィルターを追加します。  
  
    -   BTS.MessageType == **http://BasicXMLEnvelope#Error**  
  
6.  クリックして**OK**送信ポートの構成を完了します。 送信ポートが正しく構成されます。  
  
### <a name="run-the-example"></a>例の実行  
 次に、例を実行します。 BizTalk Server 管理コンソールを使用して BasicXMLEnvelope アプリケーションを起動した後、テスト ファイルを受信場所にコピーして、送信場所に生成される内容を観察します。  
  
##### <a name="to-run-the-basicxmlenvelope-example"></a>BasicXMLEnvelope 例を実行するには  
  
1.  右クリックし、BizTalk Server 管理コンソールで、 **BasicXMLEnvelope**アプリケーションをクリック**開始**します。 これにより、送信ポートと受信ポートが参加し、開始されます。  
  
2.  各サンプル ファイルを受信ディレクトリに置きます。 上記のサンプルを使用する場合は、処理された後、送信場所で 3 つの各エラー メッセージを探します。  
  
## <a name="extending-the-example"></a>例の拡張  
 この例は、他の要件に合わせて拡張できます。 このセクションでは、2 つの一般的なシナリオを取り上げます。  
  
- エラーのバッチがエンベロープで送信される場合、逆アセンブルでの個別のメッセージの失敗によって、失敗でないメッセージの処理が停止しないようにする必要があります。  
  
- エラーは、優先度に基づいて異なる場所に配信する必要があります。 優先度の高いメッセージは迅速に処理され、それ以外の優先度のメッセージは通常のチャネルで処理されます。  
  
  次のセクションでは、例を拡張してこれらの要件に適合させます。  
  
### <a name="recoverable-interchange-processing"></a>回復可能なインターチェンジ処理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、回復可能なインターチェンジ処理をサポートしています。 この機能を使用すると、逆アセンブル時のメッセージのバッチの失敗がバッチとしてではなく、個別に発生するように設定できます。  
  
##### <a name="to-configure-the-example-for-recoverable-interchange-processing"></a>回復可能なインターチェンジ処理の例を構成するには  
  
1.  BizTalk Server 管理コンソールで、 **basicxmlenvelope**アプリケーション、 をクリックして**受信ポート**、受信ポートをダブルクリックします。 これは既に作成したポートです。  
  
2.  **受信ポートのプロパティ**ダイアログ ボックスで、をクリックして**受信場所**します。 クリックして**プロパティ**を起動、 **ReceiveError 受信場所のプロパティ** ダイアログ ボックス。 省略記号をクリックします (**.**) ボタンを**受信パイプライン**します。  
  
3.  **パイプラインの構成 - XMLReceive**ダイアログ ボックスで、セット、**回復可能なインターチェンジ処理**プロパティを`True`、順にクリックします**OK**します。  
  
4.  をクリックして **[ok]** を閉じる、**受信場所のプロパティ**クリックしてダイアログ ボックスで、 **[ok]** を閉じる、**受信ポートのプロパティ**ダイアログボックス。  
  
##### <a name="to-create-a-sample-file-and-run-the-example"></a>サンプル ファイルを作成して例を実行するには  
  
1.  サンプル ファイルを作成するには、例で作成したエンベロープ サンプル ファイルのコピーを作成し、存在しない名前空間を Error インスタンスの 1 つに追加してファイルを保存します。  
  
    ```  
    <Envelope xmlns="http://BasicXMLEnvelope">  
      <Error>  
        <ID>102</ID>  
        <Type>0</Type>  
        <Priority>High</Priority>  
        <Description>Sprocket query fails to return any sprockets even though some exist</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
      <Error xmlns="http://ThisIsAnError">  
        <ID>16502</ID>  
        <Type>2</Type>  
        <Priority>Low</Priority>  
        <Description>Time threshold exceeded.</Description>  
        <ErrorDateTime>1999-05-31T13:20:00.000-05:00</ErrorDateTime>  
      </Error>  
    </Envelope>  
    ```  
  
2.  BizTalk Server 管理コンソールで、次のようにクリックします。**アプリケーション**いることを確認し、 **[basicxmlenvelope]** アプリケーションが実行されています。  
  
3.  受信場所にメッセージをドロップします。 処理後、送信場所で最初のメッセージを探し、保留キューで 2 番目のメッセージや優先度の低いメッセージを探します。  
  
### <a name="content-based-routing-cbr"></a>コンテンツ ベースのルーティング (CBR)  
 コンテンツ ベースのルーティングを使用すると、コンテンツに基づいてメッセージをルーティングできます。 このシナリオでは、優先度が “高” のメッセージは 1 つの送信場所に送られ、優先度が "中" または "低" のメッセージは別の送信場所に送られるという優先度に基づいたルーティングが行われます。  
  
 サンプルを拡張するには、次の作業を行う必要があります。  
  
1.  昇格、**優先度**BasicXMLEnvelope プロジェクトの [エラー] スキーマのフィールド。 コンテンツ ベースのルーティングでは、メッセージのルーティングに昇格させたプロパティが必要です。 詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。  
  
2.  2 つの追加の送信ポートを作成および構成します。 これらのポートでは、適切なメッセージを受信するためにフィルターを使用します。  
  
##### <a name="to-promote-the-priority-field-in-the-error-schema"></a>[エラー] スキーマの "優先度" フィールドを昇格させるには  
  
1. **[Basicxmlenvelope]** でプロジェクトを開き[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、オープン、**エラー**スキーマを展開し、**エラー**ノード。  
  
2. 右クリックし、**優先度**要素を指す**昇格**、 をクリックし、**クイック昇格**。  
  
3. クリックして**OK**昇格させたプロパティの新しいプロパティ スキーマの追加を確認します。  
  
4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、新しいプロパティ スキーマ PropertySchema.xsd を開きます。 スキーマの"Field1"を削除します。  
  
5. 次に、ソリューションを再コンパイルして再配置します。 [ビルド] メニューの [BasicXMLEnvelope の配置] を選択します。  
  
6. プロジェクトは、ソリューションが再配置されるときにホスト インスタンスを再設定するように構成されました。 これを変更した場合、ホストを停止して開始する必要があります。  
  
##### <a name="to-configure-the-low-and-medium-priority-send-port"></a>優先度が低または中程度の送信ポートを構成するには  
  
1.  "SendLowMediumPriority"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、ポートを"SendLowMediumPriority"の名前を設定します。  
  
4.  **トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。 送信先のフォルダーを、先ほど作成したディレクトリに設定します。 クリックして**OK**を閉じます。  
  
5.  クリックして**フィルター**と 3 つのフィルター式を追加します。  
  
    -   BTS します。MessageType == http://BasicXMLEnvelope#Error と  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Low Or  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == Medium  
  
6.  クリックして**OK**低または中程度の送信ポートの構成を完了します。  
  
##### <a name="to-configure-the-high-priority-send-port"></a>優先度の高い送信ポートを構成するには  
  
1.  "SendHighPriority"という名前のディレクトリを作成する Windows エクスプ ローラーを使用して、 **BasicXMLEnvelope**プロジェクト ディレクトリ。  
  
2.  BizTalk Server 管理コンソールで、 **basicxmlenvelope** 、アプリケーションを右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、ポートを"SendHighPriority"の名前を設定します。  
  
4.  **トランスポートの種類**を選択します**ファイル**、 をクリックし、**構成**します。 送信先のフォルダーを、先ほど作成したディレクトリに設定します。 クリックして**OK**を閉じます。  
  
5.  クリックして**フィルター**し、2 つのフィルター式を追加します。  
  
    -   BTS します。MessageType == http://BasicXMLEnvelope#Error と  
  
    -   BasicXMLEnvelope.PropertySchema.Priority == High  
  
6.  クリックして**OK**優先度の高い送信ポートの構成を完了します。  
  
##### <a name="to-test-the-routing-solution"></a>ソリューションのルーティングをテストするには  
  
1.  BizTalk Server 管理コンソールで、展開、**アプリケーション**グループで、右クリックし、 **[basicxmlenvelope]** アプリケーション、およびクリック**開始**。 確認するメッセージが表示されたら、クリックして**開始**します。 これにより、新しい送信ポートが参加します。  
  
2.  受信場所にテスト メッセージをドロップします。 エラー メッセージが異なる送信場所にルーティングされていることに注意してください。  
  
    -   優先度が低、中、または高に設定され、メッセージ処理を失敗していないエラー メッセージは、元の送信場所 (基本例で構成されています) と優先度に基づく送信場所の両方にルーティングされます。 優先度が低または中に設定されたメッセージでは、元の送信場所と優先度が低または中の送信場所の両方にコピーが表示されます。  
  
    -   回復可能なインターチェンジ処理が有効になっている場合、失敗したエラー メッセージのルーティングは行われませんが、失敗しなかったメッセージは想定どおり適切にルーティングされます。 失敗したメッセージがルーティングされないのは、そのメッセージの種類と、構成したフィルターで使用される種類が一致しないためです。  
  
## <a name="see-also"></a>参照  
 [回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)   
 [プロパティの昇格](../core/promoting-properties.md)   
 [CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)