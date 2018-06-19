---
title: '手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 4fe9d6fc34fa039bb4b3861deb35fb51524180ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217202"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a>手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。
![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **所要時間:** 15 分  
  
 **目標:** 今すぐ Microsoft Office SharePoint Server にアプリケーション定義ファイルをインポートし、Oracle E-business Suite からデータを取得するアプリケーションを設定する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   必要がありますがファイルを作成したアプリケーションの定義」の説明に従って[手順 2: Oracle E-business Suite 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
-   Microsoft シングル サインオン サービスを実行する必要があります。  
  
 
  
##  <a name="SSO"></a>SharePoint での SSO アプリケーションの作成  
 SharePoint アプリケーションから Oracle E-business Suite でのデータにアクセスするには、Oracle E-business Suite のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。 SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。  
  
1.  **シングル サインオンの設定をサーバー管理**です。 このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。 サーバー設定の管理 ページで、これを行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
2.  **エンタープライズ アプリケーション定義の設定を管理**です。 このステップでは、エンタープライズ アプリケーション定義の設定を構成します。 エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。  
  
    1.  サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。  
  
    2.  [操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。  
  
    3.  シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。  
  
    4.  [エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。  
  
        > [!IMPORTANT]
        >  **アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: Oracle E-business Suite 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。  
  
    5.  既定では、他のフィールドのままにし、をクリックして**OK**です。  
  
3.  **エンタープライズ アプリケーション定義のアカウント情報を管理する**です。 このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。 基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。 また、LOB システムへの接続に資格情報を指定します。 エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。 このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。 この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。  
  
##  <a name="SSP"></a>共有サービス プロバイダーを作成します。  
 共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。 SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。  
  
 SSP を作成するときに、Web サイトを定義する必要があります。 ポート番号と、サイト アドレスを作成することに注意してください。 このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。  
  
 SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。  
  
##  <a name="Import"></a>アプリケーション定義ファイルのインポート  
 SSP にアプリケーション定義ファイルをインポートする必要があります。  
  
#### <a name="to-import-the-application-definition-file"></a>アプリケーション定義ファイルをインポートするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。  
  
3.  **ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。  
  
4.  Employee.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。  
  
5.  **[インポート]** をクリックします。  
  
6.  アプリケーション定義ファイルが正常にインポートされると、クリックして**OK**です。  
  
     アプリケーション定義ファイル、MS_SAMPLE_EMPLOYEE のインポートの結果として作成されたアプリケーションが表示されます。  
  
     ![SharePoint でアプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")  
  
## <a name="next-steps"></a>次の手順  
 ここで、表示し、Oracle E-business Suite から抽出するビジネス データを検索する SharePoint サイトを作成する Web パーツを作成する準備ができたらです。 A: を作成します  
  
-   MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードを表示するビジネス データ一覧 Web パーツ。 参照してください[シナリオ 1: ビジネス データ一覧 Web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。  
  
-   MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するには、ボックス Web パーツを検索します。 参照してください[シナリオ 2: 検索ボックス Web パーツを使用して検索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)