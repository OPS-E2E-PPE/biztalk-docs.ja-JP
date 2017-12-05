---
title: "BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, WCF Service Consuming Wizard
- WCF Service Consuming Wizard
- tools, WCF Service Consuming Wizard
- consuming, WCF Service Consuming Wizard
ms.assetid: d5fad2ac-4d98-4720-8026-88ebab78b120
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb3eca6db9ceafeeab9b0b276bfd6f3cb23b16
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service"></a>BizTalk WCF サービス使用ウィザードを使用した WCF サービスの使用方法
BizTalk アダプタ フレームワークでは、アダプタ スキーマと BizTalk の型を BizTalk プロジェクトに追加する方法が提供されています。 BizTalk WCF サービス使用ウィザードを使用すると、WCF 送信アダプタを BizTalk プロジェクトに追加できます。 WCF 送信アダプタを使用するために、送信ポートに対して、既存のメタデータ交換 (MEX) エンドポイントを選択する必要があります。 次に、スキーマと型を生成するために使用する情報を入力する必要があります。 ウィザードが完了すると、WCF サービスを使用するために必要なスキーマと型が BizTalk プロジェクトに追加されます。  
  
### <a name="to-add-the-schemas-and-types-for-wcf-send-adapters-to-your-project"></a>WCF 送信アダプタのスキーマと型をプロジェクトに追加するには  
  
1.  Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト、ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、クリックして**生成した項目の追加**です。  
  
2.  **生成した項目の追加 - \<** *プロジェクト名* **\>**   ダイアログ ボックスで、**テンプレート** セクションで、選択**Consume WCF サービス**、クリックして**追加**です。  
  
3.  **BizTalk WCF サービス使用ウィザードへようこそ** ページで、をクリックして**次**です。  
  
4.  **メタデータ ソース** ページで、をクリックし、インポートするメタデータのソースを選択**次**です。  
  
     ![[メタデータ ソース] ページ](../core/media/2478a788-23ff-4ba9-a183-82e533b57f46.gif "2478a788-23ff-4ba9-a183-82e533b57f46")  
  
     実行中のサービスの metadata exchange エンドポイントからメタデータ ドキュメントをダウンロードするには、選択、 **Metadata Exchange (MEX) エンドポイント**オプション。 これにより、WCF サービスのクライアントとして機能する送信ポートを作成できます。 このオプションを使用するには、HTTP/GET または HTTPS/GET の要求を使用して取得できるように、サービス エンドポイントによってサービス メタデータが公開されていることが必要です。 また、サービス エンドポイントが、匿名ユーザー資格情報か、基本認証方式によるユーザー名とパスワードの形でのユーザー資格情報を使用したメタデータへのアクセスを許可していることも必要です。  
  
    > [!NOTE]
    >  基本認証方式では、資格情報はプレーンテキストで送信され、容易に傍受されるおそれがあります。 また、この方式では、サービスから返される情報に対する保護も提供されません。 データを暗号化するには、Secure Sockets Layer (SSL) を使用する必要があります。  
  
     他のメタデータ ドキュメントをインポートする、選択、**メタデータ ファイル (WSDL と XSD)**ファイル システムからメタデータをインポートするにはオプションです。  
  
    > [!NOTE]
    >  すべてのサービスでメタデータが公開されている必要はありません。 メタデータの公開を無効のままにすることで、サービスの攻撃対象領域が減り、意図しない情報公開の危険性が低くなります。  
  
5.  選択した場合、 **Metadata Exchange (MEX) エンドポイント** オプションを選択、**メタデータ ソース** ページで、**メタデータ エンドポイント**ページが表示されます。 **メタデータ エンドポイント**ページで、Ws-metadata Exchange または Http-get を通じてダウンロードのメタデータを提供する実行中のサービスの URL を指定します。 URL からメタデータ ドキュメントを取得する をクリックして**取得**です。 実行中のサービスは、基本認証方式でユーザーの資格情報を必要とする場合はクリックして**編集**を開くには**BizTalk WCF サービス使用ウィザード** ダイアログ ボックスでは、ユーザー名を指定することができ、サービスを実行してアクセスするときに使用するパスワードです。  
  
     ![メタデータ エンドポイント ページで](../core/media/2b17f85a-64d0-4719-99c4-ce61c706f10c.gif "2b17f85a-64d0-4719-99c4-ce61c706f10c")  
  
    > [!NOTE]
    >  HTTP または HTTPS 経由で公開された WCF サービスのメタデータをダウンロードするには、http://localhost:8087/CalculatorService/mex のなどの MEX エンドポイントを使用することはできません、**メタデータ アドレス**テキスト ボックス。 WCF サービスは、次のように、メタデータをダウンロードする WSDL メタデータを使用する必要があります: http://localhost:8087/CalculatorService または http://localhost:8087/CalculatorService? wsdl  
  
6.  選択した場合、**メタデータ ファイル (WSDL と XSD)**  オプションを選択、**メタデータ ソース** ページで、**メタデータ エンドポイント**ページが表示されます。 **メタデータ エンドポイント** ページで、インポートするメタデータ ファイルを指定します。 をクリックして**追加**にインポートするメタデータ ファイルを追加する、**メタデータ ファイル**ビュー。 開き、**メタデータ ファイルを追加**メタデータ ファイルのディスクの場所を検索するためのダイアログ ボックス。  
  
     **メタデータ ファイルを追加** ダイアログ ボックスで、WSDL と XSD の完全なセットがメタデータに使用するファイルを選択します。 これらのメタデータ ファイルを生成するには、コマンド プロンプトで以下のコマンドを入力します。  
  
     **svcutil.exe/t:metadata http://localhost/service.svc/mex**  
  
     をクリックして**削除**で選択されているメタデータ ファイルを削除する、**メタデータ ファイル**ビュー。  
  
     ![メタデータ ファイル ページ](../core/media/445bccd1-88b0-41ad-b91d-e899e7d5902d.gif "445bccd1-88b0-41ad-b91d-e899e7d5902d")  
  
    > [!NOTE]
    >  SvcUtil.exe は、Windows Vista の Microsoft Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれています。  
  
    > [!NOTE]
    >  サービス メタデータは、安全性の低い方法で取得された場合、改ざんまたは偽装される場合があります。 改ざんされたメタデータは、クライアントを悪意のあるサービスにリダイレクトしたり、侵害されたセキュリティ設定を含んでいたり、悪意のある XML 構造を含んでいたりする可能性があります。 メタデータ ドキュメントはサイズが非常に大きくなることがあり、多くの場合、ファイル システムに保存されます。 メタデータ ファイルが改ざんされていないことを確認する必要があります。  
  
7.  **WCF サービス メタデータの概要のインポート** ページで、設定を確認します。 クリックして**戻る**に変更を加えます。 をクリックして**インポート**BizTalk アイテムと、WCF サービスを使用するために使用される型を作成します。  
  
8.  **BizTalk WCF サービス使用ウィザードの完了** ページで、をクリックして**完了**です。 このウィザードを再度実行する場合は、選択、**このウィザードを再度実行**オプションをクリックして**完了**です。  
  
     BizTalk WCF サービス使用ウィザードは、BizTalk プロジェクト内に、WCF サービスを使用するために必要な BizTalk スキーマと型を作成します。 ポートの種類やマルチパート メッセージの種類などの BizTalk の型は、オーケストレーション内に作成されます。 ウィザードが作成するオーケストレーションは変更しないことをお勧めします。 変更する代わりに、目的に合った新しいオーケストレーションを BizTalk プロジェクトに追加することができます。 BizTalk WCF サービス使用ウィザードでは、2 つのバインド ファイルも作成されます**BizTalkServiceInstance.BindingInfo.xml**と**BizTalkServiceInstance_Custom.BindingInfo.xml**です。 **BizTalkServiceInstance.BindingInfo.xml**開発コマンド ライン ツールまたは標準バインド WCF アダプタと送信ポートを構成するウィザードでインポート可能な BizTalk バインド ファイルは、— たとえば、Wcf-netmsmq、Wcf-wshttpアダプター。 **BizTalkServiceInstance.BindingInfo.xml**は、開発用のコマンド ライン ツールまたは Wcf-custom アダプターと送信ポートを構成するウィザードでインポート可能な BizTalk バインド ファイルです。  
  
     設定されます、生成されたバインド ファイルをインポートするときに、 **WCF です。アクション**アクション マッピング形式でのプロパティです。 このプロパティを構成する方法を表示するを見て、**アクション**上のテキスト ボックス、**全般** タブで、WCF 送信ポート トランスポートのプロパティ ダイアログ ボックス、BizTalk 管理コンソールでします。  
  
     指定することができます、 **WCF です。アクション**2 つの異なる方法でのプロパティ: シングル アクション形式とアクション マッピング形式です。 シングル アクション形式 http://contoso.com/Svc/Op1 など、このプロパティを設定する場合、 **SOAPAction**ヘッダーは常に送信メッセージの値に設定、このプロパティで指定します。 送信アクション マッピング形式でこのプロパティを設定する場合**SOAPAction**ヘッダーはによって決定されます、 **BTS です。操作**コンテキスト プロパティです。 たとえば、このプロパティは、次の XML 形式に設定されている場合、 **BTS です。操作**プロパティに設定されている**Op1**、WCF 送信アダプタでは、http://contoso.com/Svc/Op1 を使用、送信を**SOAPAction**ヘッダー。  
  
     `<BtsActionMapping>`  
  
     `<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" />`  
  
     `<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" />`  
  
     `</BtsActionMapping>`  
  
     送信メッセージ ソース場合オーケストレーション ポートから、オーケストレーション インスタンスに動的に設定して、 **BTS です。操作**ポートの操作の名前を持つプロパティです。 コンテンツ ベースのルーティングと、送信メッセージのルーティングされる場合は、設定、 **BTS です。操作**パイプライン コンポーネントのプロパティです。 BizTalk WCF 使用ウィザードで生成されたポートと一致する名前の操作がある、**名前**属性で、  **<BtsActionMapping>** 要素。 明示的に設定する必要はありません、 **BTS です。操作**ウィザードによって生成されたポートを通じてメッセージを送信するときは、オーケストレーション内のプロパティです。  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)   
 [BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)