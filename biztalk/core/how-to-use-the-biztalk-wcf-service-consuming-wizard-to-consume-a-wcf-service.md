---
title: BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Consuming Wizard
- WCF Service Consuming Wizard
- tools, WCF Service Consuming Wizard
- consuming, WCF Service Consuming Wizard
ms.assetid: d5fad2ac-4d98-4720-8026-88ebab78b120
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c626e171135332bca35845c99fc477bbc0e9a60b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009299"
---
# <a name="how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service"></a>BizTalk WCF サービス使用ウィザードを使用した WCF サービスの使用方法
BizTalk アダプタ フレームワークでは、アダプタ スキーマと BizTalk の型を BizTalk プロジェクトに追加する方法が提供されています。 BizTalk WCF サービス使用ウィザードを使用すると、WCF 送信アダプタを BizTalk プロジェクトに追加できます。 WCF 送信アダプタを使用するために、送信ポートに対して、既存のメタデータ交換 (MEX) エンドポイントを選択する必要があります。 次に、スキーマと型を生成するために使用する情報を入力する必要があります。 ウィザードが完了すると、WCF サービスを使用するために必要なスキーマと型が BizTalk プロジェクトに追加されます。  
  
### <a name="to-add-the-schemas-and-types-for-wcf-send-adapters-to-your-project"></a>WCF 送信アダプタのスキーマと型をプロジェクトに追加するには  
  
1. Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**生成した項目の追加**します。  
  
2. **生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**Consume WCF サービス**、 をクリックし、**追加**します。  
  
3. **BizTalk WCF サービス使用ウィザードへようこそ**] ページで [**次**します。  
  
4. **メタデータ ソース** をクリックし、インポートするメタデータのソースの選択 ページで、**次**します。  
  
    ![メタデータ ソース ページ](../core/media/2478a788-23ff-4ba9-a183-82e533b57f46.gif "2478a788-23ff-4ba9-a183-82e533b57f46")  
  
    実行中のサービスの metadata exchange エンドポイントからメタデータ ドキュメントをダウンロードするには、選択、 **Metadata Exchange (MEX) エンドポイント**オプション。 これにより、WCF サービスのクライアントとして機能する送信ポートを作成できます。 このオプションを使用するには、HTTP/GET または HTTPS/GET の要求を使用して取得できるように、サービス エンドポイントによってサービス メタデータが公開されていることが必要です。 また、サービス エンドポイントが、匿名ユーザー資格情報か、基本認証方式によるユーザー名とパスワードの形でのユーザー資格情報を使用したメタデータへのアクセスを許可していることも必要です。  
  
   > [!NOTE]
   >  基本認証方式では、資格情報はプレーンテキストで送信され、容易に傍受されるおそれがあります。 また、この方式では、サービスから返される情報に対する保護も提供されません。 データを暗号化するには、Secure Sockets Layer (SSL) を使用する必要があります。  
  
    他のメタデータ ドキュメントをインポートする、選択、**メタデータ ファイル (WSDL と XSD)** ファイル システムからメタデータをインポートするオプション。  
  
   > [!NOTE]
   >  すべてのサービスでメタデータが公開されている必要はありません。 メタデータの公開を無効のままにすることで、サービスの攻撃対象領域が減り、意図しない情報公開の危険性が低くなります。  
  
5. 選択した場合、 **Metadata Exchange (MEX) エンドポイント**オプションを**メタデータ ソース** ページで、**メタデータ エンドポイント**ページが表示されます。 **メタデータ エンドポイント**ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定します。 URL からメタデータ ドキュメントを取得する次のようにクリックします。**取得**します。 実行中のサービスには、基本認証スキームでユーザーの資格情報が必要とする場合にクリックします**編集**を開く**BizTalk WCF サービス使用ウィザード** ダイアログ ボックスのユーザー名を入力し、サービスを実行してアクセスするときに使用するパスワード。  
  
    ![メタデータ エンドポイント ページ](../core/media/2b17f85a-64d0-4719-99c4-ce61c706f10c.gif "2b17f85a-64d0-4719-99c4-ce61c706f10c")  
  
   > [!NOTE]
   >  HTTP または HTTPS 経由で公開された WCF サービスのメタデータをダウンロードするには、使うことはできません、MEX エンドポイントなど http://localhost:8087/CalculatorService/mex の **メタデータ アドレス** テキスト ボックス。 WCF サービスは、次のように、メタデータをダウンロードする WSDL メタデータを使用する必要があります: http://localhost:8087/CalculatorService または http://localhost:8087/CalculatorService?wsdl  
  
6. 選択した場合、**メタデータ ファイル (WSDL と XSD)** オプションを**メタデータ ソース** ページで、**メタデータ エンドポイント**ページが表示されます。 **メタデータ エンドポイント**ページで、インポートするメタデータ ファイルを指定します。 クリックして**追加**にインポートするメタデータ ファイルを追加する、**メタデータ ファイル**ビュー。 開き、**メタデータ ファイルの追加**メタデータ ファイルのディスクの場所を検索するためのダイアログ ボックス。  
  
    **メタデータ ファイルの追加** ダイアログ ボックスで、メタデータに使用する WSDL と XSD の完全なセットがファイルを選択します。 これらのメタデータ ファイルを生成するには、コマンド プロンプトで以下のコマンドを入力します。  
  
    **svcutil.exe/t:metadata http://localhost/service.svc/mex**  
  
    クリックして**削除**で選択したメタデータ ファイルを削除する、**メタデータ ファイル**ビュー。  
  
    ![メタデータ ファイル ページ](../core/media/445bccd1-88b0-41ad-b91d-e899e7d5902d.gif "445bccd1-88b0-41ad-b91d-e899e7d5902d")  
  
   > [!NOTE]
   >  SvcUtil.exe は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれています。  
  
   > [!NOTE]
   >  サービス メタデータは、安全性の低い方法で取得された場合、改ざんまたは偽装される場合があります。 改ざんされたメタデータは、クライアントを悪意のあるサービスにリダイレクトしたり、侵害されたセキュリティ設定を含んでいたり、悪意のある XML 構造を含んでいたりする可能性があります。 メタデータ ドキュメントはサイズが非常に大きくなることがあり、多くの場合、ファイル システムに保存されます。 メタデータ ファイルが改ざんされていないことを確認する必要があります。  
  
7. **WCF サービス メタデータの概要のインポート**ページで、設定を確認します。 クリックすることができます**戻る**変更を加えます。 クリックして**インポート**BizTalk アイテムと、WCF サービスを使用するために使用される型を作成します。  
  
8. **BizTalk WCF サービス使用ウィザードの完了**] ページで [**完了**します。 このウィザードを再度実行する場合は、選択、**このウィザードを再度実行**オプションをクリックして**完了**します。  
  
    BizTalk WCF サービス使用ウィザードは、BizTalk プロジェクト内に、WCF サービスを使用するために必要な BizTalk スキーマと型を作成します。 ポートの種類やマルチパート メッセージの種類などの BizTalk の型は、オーケストレーション内に作成されます。 ウィザードが作成するオーケストレーションは変更しないことをお勧めします。 変更する代わりに、目的に合った新しいオーケストレーションを BizTalk プロジェクトに追加することができます。 BizTalk WCF サービス使用ウィザードでは、2 つのバインド ファイルも作成されます**BizTalkServiceInstance.BindingInfo.xml**と**BizTalkServiceInstance_Custom.BindingInfo.xml**します。 **BizTalkServiceInstance.BindingInfo.xml**コマンド ライン ツールの開発や、標準バインド WCF アダプタと送信ポートを構成するウィザードでインポート可能な BizTalk バインド ファイルには、Wcf-netmsmq と Wcf-wshttp などアダプター。 **BizTalkServiceInstance.BindingInfo.xml**はコマンド ライン ツールの開発や、Wcf-custom アダプターと送信ポートを構成するウィザードでインポートできる BizTalk バインド ファイルです。  
  
    生成されたバインド ファイルをインポートすると、 **WCF です。アクション**アクション マッピング形式でのプロパティ。 このプロパティを構成する方法を確認してを参照、**アクション**上のテキスト ボックス、**全般** タブで、WCF 送信ポート トランスポート プロパティ ダイアログ ボックスで、BizTalk 管理コンソール。  
  
    指定することができます、 **WCF です。アクション**2 つの方法でのプロパティ: シングル アクション形式とアクション マッピング形式。 たとえば、1 つのアクションの形式でこのプロパティを設定する場合 http://contoso.com/Svc/Op1 - **SOAPAction**このプロパティで指定された値を設定は常に送信メッセージのヘッダー。 送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS します。操作**コンテキスト プロパティ。 たとえば、次の XML 形式にこのプロパティが設定されている場合、 **BTS します。操作**プロパティに設定されて**Op1**、WCF 送信アダプタが使用 http://contoso.com/Svc/Op1 アウトゴーイング**SOAPAction**ヘッダー。  
  
    `<BtsActionMapping>`  
  
    `<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" />`  
  
    `<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" />`  
  
    `</BtsActionMapping>`  
  
    送信メッセージは、オーケストレーション ポートからに関しては場合、オーケストレーション インスタンスは動的に設定、 **BTS します。操作**ポートの操作の名前を持つプロパティです。 設定することができますコンテンツ ベースのルーティングでは、送信メッセージがルーティングされている場合、 **BTS します。操作**パイプライン コンポーネントのプロパティ。 BizTalk WCF 使用ウィザードで生成されたポートと一致する名前の操作がある、**名前**属性、 **<BtsActionMapping>** 要素。 明示的に設定する必要はありません、 **BTS します。操作**ウィザードによって生成されたポートを通じてメッセージを送信するときは、オーケストレーションのプロパティ。  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)   
 [BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)