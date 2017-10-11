---
title: "SAP 用のレポートの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d446a24ca9432842d52062acb494f92060bbaaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="view-the-reports-for-sap"></a>SAP 用のレポートを表示します。
レポートを作成した後、それを表示できる Visual Studio を使用するか、ネットワーク経由でインターネット インフォメーション サービス (IIS) とアクセスでレポート サーバー上でホストします。 このトピックでは、Visual Studio および IIS を使用して両方のレポートを表示する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前にする必要がありますが生成したレポート」の説明に従って[SAP 用データ プロバイダーを使用してレポート サーバー プロジェクトを作成](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)です。  
  
### <a name="to-view-the-reports-in-visual-studio"></a>Visual Studio でレポートを表示するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、クリックして**プロパティ**です。  
  
2.  レポート プロパティ ページ ダイアログ ボックスをクリックして**Configuration Manager**、下のチェック ボックスをオフにし、**展開**列です。 **[閉じる]**をクリックします。  
  
3.  レポート プロパティ ページ ダイアログ ボックスの**StartItem**プロパティ、レポートの名前を選択し、をクリックして**OK**です。  
  
     ![レポート サーバー プロジェクトのプロパティを指定](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")  
  
4.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。  
  
5.  キーを押して`F5`レポートを生成するプロジェクトを実行します。  
  
    > [!IMPORTANT]
    >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]をクリックして、レポートを見ることができます、**プレビュー**タブです。このような場合は、[プレビュー] タブ内の後続のダイアログ ボックスが開きます。  
  
6.  レポートに対して指定したのと同じ名前のダイアログ ボックスが開きます。 選択した場合、データ ソースの作成中に、**資格情報の入力を求める**オプションを SAP システムのユーザー名とパスワードを入力してをクリックして**レポートの表示**です。  
  
     ![レポートを生成する SAP 資格情報を指定](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")  
  
7.  クエリを指定した場合、パラメーター、レポート サーバー プロジェクトを作成する必要があります、パラメーターの値を入力する必要があります。 たとえばで指定したクエリの[SAP 用データ プロバイダーを使用してレポート サーバー プロジェクトを作成](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。  
  
     必要な場合、パラメーターの値を指定し、クリックして**レポートの表示**です。  
  
     ![レポートを生成するパラメーターを指定](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")  
  
### <a name="to-host-the-reports-on-report-server"></a>レポート サーバー上のレポートをホストするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、クリックして**プロパティ**です。  
  
2.  レポート プロパティ ページ ダイアログ ボックスをクリックして**Configuration Manager**、下にあるチェック ボックスをオンにし、**展開**列です。 **[閉じる]**をクリックします。  
  
3.  レポート プロパティ ページ ダイアログ ボックスの**StartItem**プロパティ、レポートの名前を選択します。  
  
4.  レポート プロパティ ページ ダイアログ ボックスの**TargetServerURL**プロパティ、レポート サーバーの URL を指定し、をクリックして**OK**です。 例:  
  
    ```  
    http://localhost/reportserver  
    ```  
  
     ![レポート サーバーの URL の指定](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")  
  
5.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。  
  
6.  ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。  
  
7.  IIS を起動します。 をクリックして**開始**、 をクリックして**実行**、型`inetmgr`、キーを押します`Enter`です。  
  
8.  **インターネット インフォメーション サービス (IIS) マネージャー**スナップインで、コンピューター名を展開、展開**Websites**、展開**既定の Web サイト**を右クリックして**ReportServer**、クリックして**参照**です。  
  
9. 右側のウィンドウで、プロジェクトの名前をクリックし、レポートの名前をクリックします。  
  
10. 選択した場合、データ ソースの作成中に、**資格情報の入力を求める**オプションを SAP システムのユーザー名とパスワードを入力してをクリックして**レポートの表示**です。  
  
11. クエリを指定した場合、パラメーター、レポート サーバー プロジェクトを作成する必要があります、パラメーターの値を入力する必要があります。 たとえばで指定したクエリの[SAP 用データ プロバイダーを使用してレポート サーバー プロジェクトを作成](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。  
  
     必要な場合、パラメーターの値を指定し、クリックして**レポートの表示**です。  
  
     ![レポートを生成するパラメーターを指定](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")  
  
    > [!TIP]
    >  レポートの URL を提供することにより、web ブラウザーから直接表示することもできます。 レポートの一般的な URL`is http://localhohost/reportserver/<report_name>`です。  
  
## <a name="see-also"></a>参照  
 [SSRS と SAP 用データ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)