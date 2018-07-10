---
title: SAP のため、レポートの表示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8643ef37e3fe4aec77cd9d218a171d37c2c24852
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974611"
---
# <a name="view-the-reports-for-sap"></a>SAP のため、レポートを表示します。
表示できるレポートを作成した後 Visual Studio を使用するか、ネットワーク経由でインターネット インフォメーション サービス (IIS) とアクセス上のレポート サーバー上でホストします。 このトピックでは、Visual Studio と IIS を使用して両方でレポートを表示する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このトピックで説明する手順を実行する前にする必要がありますが生成したレポート」の説明に従って[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)します。  
  
### <a name="to-view-the-reports-in-visual-studio"></a>Visual Studio でレポートを表示するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、[クリックして**プロパティ**します。  
  
2. レポート プロパティ ページ] ダイアログ ボックスで次のようにクリックします。 **Configuration Manager**、下のチェック ボックスをオフにし、**デプロイ**列。 **[閉じる]** をクリックします。  
  
3. レポート プロパティ ページ] ダイアログ ボックスの **[startitem]** プロパティが、レポートの名前を選択し、クリックして**OK**。  
  
    ![レポート サーバー プロジェクトのプロパティを指定](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")  
  
4. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**ビルド**します。  
  
5. キーを押して`F5`レポートを生成するプロジェクトを実行します。  
  
   > [!IMPORTANT]
   >  [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]、] をクリックして、レポートを表示できます、**プレビュー**タブ。このような場合は、[プレビュー] タブ内で以降のダイアログ ボックスが開きます。  
  
6. レポートの指定した同じ名前のダイアログ ボックス開きます。 選択した場合、データ ソースを作成するときに、**資格情報の入力を求める**オプションで、SAP システムのユーザー名とパスワードを入力します。 をクリック**レポートの表示**します。  
  
    ![レポートを生成する SAP 資格情報を指定](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")  
  
7. クエリを指定した場合、レポート サーバー プロジェクトを作成するには、パラメーターが必要です。 中にパラメーターの値を入力する必要があります。 たとえばで指定したクエリの[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。  
  
    必要な場合に、パラメーターの値を指定し、クリックして**レポートの表示**します。  
  
    ![レポートを生成するパラメーターを指定する](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")  
  
### <a name="to-host-the-reports-on-report-server"></a>レポート サーバーでレポートをホストするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでプロジェクト名を右クリックし、[クリックして**プロパティ**します。  
  
2. レポート プロパティ ページ] ダイアログ ボックスで次のようにクリックします。 **Configuration Manager**、下のチェック ボックスを選択し、**デプロイ**列。 **[閉じる]** をクリックします。  
  
3. レポート プロパティ ページ] ダイアログ ボックスの**StartItem**プロパティ、レポートの名前を選択します。  
  
4. レポート プロパティ ページ] ダイアログ ボックスの**TargetServerURL**プロパティ、レポート サーバーの URL を指定し、順にクリックします**OK**します。 以下に例を示します。  
  
   ```  
   http://localhost/reportserver  
   ```  
  
    ![レポート サーバーの URL の指定](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")  
  
5. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**ビルド**します。  
  
6. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、**デプロイ**します。  
  
7. IIS を起動します。 クリックして**開始**、] をクリックして**実行**、型`inetmgr`、キーを押します`Enter`します。  
  
8. **インターネット インフォメーション サービス (IIS) マネージャー**スナップインで、コンピューター名を展開し、 **Websites**、展開**既定の Web サイト**、右クリック**ReportServer**、] をクリックし、**参照**します。  
  
9. 右側のウィンドウで、プロジェクトの名前をクリックし、レポートの名前をクリックします。  
  
10. 選択した場合、データ ソースを作成するときに、**資格情報の入力を求める**オプション、SAP システムのユーザー名とパスワードを入力します] をクリックして**レポートの表示**します。  
  
11. クエリを指定した場合、レポート サーバー プロジェクトを作成するには、パラメーターが必要です。 中にパラメーターの値を入力する必要があります。 たとえばで指定したクエリの[Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md)トピックでは、パラメーター、パラメーターの値を指定する必要があります。  
  
     必要な場合に、パラメーターの値を指定し、クリックして**レポートの表示**します。  
  
     ![レポートを生成するパラメーターを指定する](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")  
  
    > [!TIP]
    >  レポートの URL を指定することにより、web ブラウザーから直接表示することもできます。 レポートの一般的な URL`is http://localhohost/reportserver/<report_name>`します。  
  
## <a name="see-also"></a>参照  
 [Data Provider for SAP を SSRS と一緒に使用する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)