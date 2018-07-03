---
title: 方法を使用して、BizTalk Web サービス公開ウィザード Web サービスとしてのスキーマを公開する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard, schemas
ms.assetid: b22de720-1416-486a-988f-e52527ad9ab1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7a6f0ed34fe14db9e751d7f29efba443944932a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975795"
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-schemas-as-a-web-service"></a>BizTalk Web サービス公開ウィザードを使用してスキーマを Web サービスとして公開する方法
BizTalk Web サービス公開ウィザードを使用して、スキーマを Web サービスとして公開することができます。  
  
### <a name="to-publish-schemas-as-a-web-service"></a>スキーマを Web サービスとして公開するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Web サービス公開ウィザード**します。  
  
   > [!IMPORTANT]
   >  BizTalk Web サービス公開ウィザードを実行する前に、BizTalk プロジェクトをビルドする必要があります。  
  
2. **へようこそ**  ページで **次**します。  
  
3. **Web サービスの作成**] ページで、[**スキーマを web サービスとして公開**順にクリックします**次**します。  
  
4. **Web サービス**ページで、公開する Web サービスを定義します。 ツリーを使用して、 **Web サービスの説明**を追加、削除、名前の変更、および Web サービス説明ノードの編集 ダイアログ ボックス。 **情報** ダイアログ ボックスが選択したノードに関する情報し、現在のノードまたはサブノードでエラーが表示されます。  
  
   -   ツリーのルート ノード (Web サービスの説明) には、Web サービスのプロジェクト名が使用されます。 仮想ディレクトリ名では、ルート ノードが既定の名前として使用されます。 Web サービスの説明を選択して変更できます**web サービスの説明の名前を変更**します。  
  
   -   新しい Web サービスを追加するには、右クリックし、 **Web サービスの説明**ノードをクリック**web サービスの追加**します。 Web メソッドを指定しない新しい Web サービスが作成されます。 Web サービスの名前を変更するには、Web サービスのノードを右クリックして**web サービスの名前を変更**、し、enter キーを押して新しい名前を受け入れます。  
  
   -   新しい Web メソッドを追加するには、Web サービスのノードを右クリックし、 をポイント**Web メソッドの追加**、順にクリックします**一方向**(要求 Web メソッドの場合) 用または**要求-応答**(用、要求-応答 Web メソッドの場合)、ショートカット メニューから。  
  
   -   要求と応答スキーマの種類を設定するには、右、**要求**または**応答**ノードをクリック**スキーマの種類の選択**します。 **要求メッセージの種類**] ダイアログ ボックスに、ドキュメント スキーマを格納しているアセンブリの名前を入力、 **BizTalk アセンブリ ファイル**テキスト ボックスまたは [**参照**を検索するにはアセンブリ。 **使用可能なスキーマ型**リスト ビューには、スキーマの場合は、各ルート要素が表示されます。 要求または応答のスキーマの種類として追加するルート ノードを選択します。  
  
       > [!NOTE]
       >  BizTalk アセンブリ ファイルをグローバル アセンブリ キャッシュ (GAC) にインストールした場合に選択するアセンブリを GAC にアセンブリが更新されたこと確認、**要求メッセージの種類** ダイアログ ボックス。 GAC の完全修飾名が同じである場合、BizTalk Web サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
   -   名前を変更することができます、**要求**と**応答**ノードは、生成されたコードには影響しません。 スキーマを定義した後、部分要素の名前を変更することができ、これにより Web メソッド パラメータの名前が変更されます。 生成された Web サービス コードを表示することで、変更内容を確認できます。  
  
   > [!NOTE]
   >  Web サービス説明ノードの名前を変更するとき、空白文字は使用できません。  
  
5. クリックして**次**ウィザードを続行します。  
  
6. **Web サービスのプロパティ**ページで、 **web サービスのターゲット名前空間** ダイアログ ボックスでは、Web サービスのターゲットの名前空間を入力し、ウィザードがどのように指定する適切なボックスを選択しますSOAP ヘッダーと Web サービスのシングル サインオン サポートを処理します。 Web サービスの実装をさらにカスタマイズする場合は、クリックして**詳細**ボタンをクリックします。 次の詳細設定オプションが表示されます。  
  
   |オプション|値|説明|  
   |------------|-----------|-----------------|  
   |SOAP パラメーターの書式|既定|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)します。|  
   |SOAP パラメーターの書式|Bare|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)します。|  
   |SOAP パラメーターの書式|Wrapped|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)します。|  
   |適合性表示|なし|バインド要求が準拠する Web サービスの相互運用性 (WSI) 仕様を指定します。 詳細については、「WebServiceBindingAttribute.ConformsTo プロパティを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)します。|  
   |適合性表示|WS-I 基本プロファイル 1.1|バインド要求が準拠する Web サービスの相互運用性 (WSI) 仕様を指定します。 詳細については、「WebServiceBindingAttribute.ConformsTo プロパティを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)します。|  
   |要求 - 応答を強制|[Default]|一方向の BizTalk 操作を要求 - 応答 Web メソッドとして公開するかどうかを指定します。 既定では、一方向のフラグは強制されません。|  
  
   > [!NOTE]
   >  いずれかの SOAP ヘッダー オプションを選択すると、そのオプションは、ウィザードのこのインスタンスの実行時に作成されたすべての Web サービスおよび Web メソッドにグローバルに適用されます。  
  
7. **Web サービスのプロパティ**] ページで [**次**します。  
  
8. 選択した場合**追加の SOAP ヘッダーを追加**、**要求 SOAP ヘッダー**と**応答 SOAP ヘッダー**ページが表示されます。 追加およびを使用して要求と応答の SOAP ヘッダーを削除することができます、**追加**と**削除**以下のダイアログ ボックスのボタン。  
  
   -   SOAP ヘッダーを追加する をクリックして**追加**します。 **BizTalk アセンブリ名 (\*.dll)** テキスト ボックスに、アセンブリ名を入力するかで SOAP ヘッダー スキーマを含むアセンブリの参照、 **BizTalk アセンブリ ファイル**テキスト ボックス。 **使用可能なスキーマ型**リスト ビューには、スキーマの場合は、各ルート要素が表示されます。 要求または応答の SOAP ヘッダーとして追加するルート ノードを選択します。 複数の項目を選択するには、CTRL キーを押しながらと をクリックして**OK**します。  
  
   -   SOAP ヘッダーの一覧からを削除する追加の SOAP ヘッダーの一覧から選択をクリックして**削除**します。  
  
   -   クリックして**次**ウィザードを続行する各 SOAP ヘッダーのページ。  
  
   > [!NOTE]
   >  ターゲットの名前空間とルート要素名は、SOAP ヘッダーを定義します。  
  
   > [!NOTE]
   >  対象となる名前空間とルート要素名の同じ組み合わせを要求および応答 SOAP ヘッダーとして追加すると、受信および送信ヘッダーとして扱われません。 オーケストレーション内で受信ヘッダーを送信ヘッダーに手動でコピーする必要があります。  
  
   > [!NOTE]
   >  対象となる名前空間とルート要素名の同じ組み合わせは、要求 SOAP ヘッダーとして 1 度、応答 SOAP ヘッダーとして一度だけ追加できます。  
  
9. **Web サービス プロジェクト**ページで、**プロジェクトの場所**テキスト ボックスに、プロジェクトの場所を入力します。 既定の場所を受け入れることができます (http://localhost/<*project_name*>)、プロジェクトの場所を入力またはクリックして**参照**Web ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    -   **既存のプロジェクトを上書きします。** : このオプションは、プロジェクトの場所が既に存在する場合にのみ使用できます。 このオプションを選択した場合、同じ場所に発行することのみできます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    -   **Web サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
    -   **作成する BizTalk 受信場所。** このオプションでは、生成された各 .asmx ファイルに対応する SOAP アダプターの受信ポートと受信場所が自動的に作成されます。 別の受信場所が既に存在する場合、受信場所は置き換えられません。 SOAP アダプターを解決する形式を使用して、受信場所"/\<*仮想ディレクトリ名*\>/\<*オーケストレーション namespace_typename_portname* \>.asmx"。 このオプションの選択後、受信ポートと場所を生成するアプリケーションを選択します。  
  
        > [!NOTE]
        >  プロジェクトの場所には、別のサーバーを指定することもできます。 Web サービスを別のサーバーに発行するには、としてプロジェクト名を入力**http://&lt*servername*>/<*project_name*>** します。  
  
        > [!NOTE]
        >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに発行するときは、URL に Web サイトのポート番号を含める: http://localhost:8080/< *project_name*>。  
  
        > [!NOTE]
        >  ウィザードを使用して受信場所を作成する場合は、既定値が多く使用されます。 受信および送信パイプラインの既定値は**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**と**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。 かどうか、公開済み Web サービスを通じて受信するメッセージが、特別なパイプライン処理 (検証、関連付け、または受信/送信マップなど) を必要とし、設定、送信と受信パイプラインをする必要があります**Microsoft.BizTalk.DefaultPipelines.XMLReceive**、 **Microsoft.BizTalk.DefaultPipelines.XMLSend**、またはカスタム パイプラインです。  
  
10. クリックして**次**ASP.NET Web サービス プロジェクトの設定を確認します。  
  
11. クリックして**作成**ASP.NET Web サービスを作成します。  
  
12. クリックして**完了**BizTalk Web サービス公開ウィザードを完了します。  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのスキーマの公開](../core/publishing-schemas-as-a-web-service.md)