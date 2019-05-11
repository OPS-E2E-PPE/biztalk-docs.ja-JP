---
title: 手順 3:Oracle E-business Suite からデータを取得する SharePoint アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaa16011-9284-4ccf-8132-9c1e14cc6aa7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baaaa68a372900304ec9a776a49f46e0623d71cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374554"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a>手順 3:Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 **目標:** Microsoft Office SharePoint server、アプリケーション定義ファイルをインポートし、Oracle E-business Suite からデータを取得するアプリケーションを設定する必要がありますようになりました。  
  
## <a name="prerequisites"></a>前提条件  
  
-   作成済みアプリケーション定義ファイル」の説明に従って[手順 2。Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
 
  
##  <a name="SSO"></a> SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションから Oracle E-business Suite 内のデータにアクセスするには、ユーザーが Oracle E-business Suite、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint での SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**します。 この手順では、管理、シングル サインオン サービスを設定しているユーザー アカウントを指定します。 管理サーバーの設定 ページで行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「構成でシングル サインオン Office SharePoint Server 2007 の」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理する**します。 この手順では、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。  
  
    2.  操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。  
  
    3.  シングル サインオン ページで、設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、**企業アプリケーション定義の設定を管理する**します。  
  
    4.  エンタープライズ アプリケーション定義の管理 ページで、値を指定、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールド。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定したのと同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルを作成するときに変数説明されている[手順 2。Oracle E-business Suite の成果物のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
    5.  既定では、他のフィールドのままにし、クリックして**OK**します。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報の管理**します。 この手順では SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップするか、個々 のユーザーまたはグループをユーザーに、LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。 このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。 この手順の詳細については、ある「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。  
  
##  <a name="SSP"></a> 共有サービス プロバイダーを作成します。  
 共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。 SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。  
  
 SSP を作成するときに、Web サイトを定義する必要があります。 ポート番号とを作成するサイトのアドレスに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、次を参照してください。"」の章の概要。作成および共有サービス プロバイダーの構成"に[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)します。  
  
##  <a name="Import"></a> アプリケーション定義ファイルのインポート  
 SSP に今すぐアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。  
  
4.  Employee.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、**オープン**します。  
  
5.  **[インポート]** をクリックします。  
  
6.  アプリケーション定義ファイルが正常にインポートされると、クリックして**OK**します。  
  
     MS_SAMPLE_EMPLOYEE をアプリケーション定義ファイルのインポートの結果として作成されたアプリケーションが表示されます。  
  
     ![Sharepoint アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")  
  
## <a name="next-steps"></a>次の手順  
 ここで、表示され、Oracle E-business Suite から抽出するビジネス データを検索するには、SharePoint サイトを作成する Web パーツを作成する準備が整ったらします。 A: を作成します  
  
-   MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードを表示するビジネス データ一覧 Web パーツ。 参照してください[シナリオ 1。ビジネス データ一覧 Web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)します。  
  
-   検索ボックス Web パーツ MS_SAMPLE_EMPLOYEE インターフェイス テーブルのフルテキスト検索を実行します。 参照してください[シナリオ 2。検索ボックス Web パーツを使用して検索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)