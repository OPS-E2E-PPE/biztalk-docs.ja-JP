---
title: "SAP 用データ プロバイダーを使用してレポート サーバー プロジェクトを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caa006e8c8e22b10d0bdc58a781de30a0623bb79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a>SAP 用データ プロバイダーを使用してレポート サーバー プロジェクトを作成
レポート サーバーを作成する必要がありますを使用して、プロジェクト、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、SAP システムで使用できるデータのレポートを生成します。 このトピックでは、レポート サーバー プロジェクトを作成する方法についてを説明します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックに記載されている手順を実行する前に、インストールを確認してください、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]のインストール中に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。 詳細については[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールで使用可能なインストール ガイドを参照してください\<*インストール ドライブ*>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。  
  
### <a name="to-create-a-report-server-project"></a>レポート サーバー プロジェクトを作成するには  
  
1.  開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]レポート サーバー プロジェクトを作成します。 レポート サーバー プロジェクトを作成するには、次の操作を行います。  
  
    1.  クリックして、**ファイル** メニューのをクリックして**新規**、順にクリック**プロジェクト**です。  
  
    2.  **新しいプロジェクト**] ダイアログ ボックスから、**プロジェクトの種類**一覧で、[**ビジネス インテリジェンス プロジェクト**です。 **、Visual Studio にインストールされたテンプレート**一覧で、**レポート サーバー プロジェクト**です。  
  
    3.  プロジェクトの場所と名前を指定し、クリックして**OK**です。 このトピックでは、としてプロジェクトの名前を指定`SAP_ Report`です。  
  
2.  新しいデータ ソースを追加します。  
  
    1.  ソリューション エクスプ ローラーから右**共有データ ソース**、 をクリック**新しいデータ ソースの追加**です。  
  
    2.  **共有データ ソース** ダイアログ ボックスで、**全般** タブで、データ ソースの名前を指定します。 このトピックの名前を指定、として`SAPDataSource`です。  
  
    3.  **型**一覧で、 **Data Provider 用 SAP**です。  
  
    4.  **接続文字列**ボックスでの接続文字列を指定、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。 については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]接続文字列を参照してください[SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。  
  
         ![データ ソースを作成](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")  
  
        > [!NOTE]
        >  接続文字列の一部として、資格情報を指定するか、次の手順で説明したように指定することができます。  
  
    5.  **資格情報** タブで、次のいずれかを選択し、をクリックして**OK**:  
  
        |プロパティ|目的|  
        |--------------|----------------|  
        |**[特定のユーザー名とパスワードを使用する]**|ユーザー名と、SAP システムへの接続にパスワードを指定します。|  
        |**資格情報の入力を求める**|レポートの生成時に、SAP システムの資格情報を入力します。 **注:**資格情報を指定する接続文字列の一部として、指定した場合、資格情報の上書きは、このオプションにします。|  
        |**資格情報なし**|接続文字列の一部として、ユーザー名とパスワードを指定する場合は、このオプションを選択します。|  
  
        > [!NOTE]
        >  レポート サーバー プロジェクトには、Windows 認証モードがサポートされていません。  
  
3.  新しいレポートを追加します。  
  
    1.  ソリューション エクスプ ローラーから右**レポート**、順にクリック**新しいレポートの追加**です。  
  
         これにより、レポート ウィザードが起動します。  
  
    2.  [ようこそ] 画面で、情報を参照し、をクリックして**次**です。  
  
    3.  **データ ソースを選択** ダイアログ ボックスで、選択、**共有データ ソース**オプションを選択、 **SAPDataSource**前の手順で作成し、 をクリックして**次へ**です。  
  
    4.  選択した場合、**資格情報の入力を求める**データ ソースの作成中にユーザーの資格情報を指定するオプション、**データ ソースの資格情報の入力** ダイアログ ボックスが表示されます。 ユーザー名と、SAP システムに接続し、をクリックするパスワードを指定**OK**です。  
  
         資格情報を指定するため、他のオプションを選択した場合、ウィザードは次の手順に進みます。  
  
    5.  **クエリをデザイン** ダイアログ ボックスで、レポートを生成するために使用するクエリ文字列を指定します。 例:  
  
        ```  
        SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
        ```  
  
         このクエリは上の 2 つのレコード テーブルから取得 KNA1、NAME1 はするが、レポートの生成中に指定する名前を指定します。  
  
         **[次へ]**をクリックします。  
  
    6.  以降のダイアログ ボックスでは、レポートを表示する形式をデザインできます。 既定の形式を使用する場合をクリックして**完了 >> &#124;**に直接移動する、**完了** ダイアログ ボックス。  
  
    7.  **ウィザードの完了**ダイアログ ボックスで、レポートの名前を指定の概要を確認し、**完了**です。 このトピックのため、レポートの名前を指定`SAPReport`です。  
  
     レポートを表示できるようになりました。 レポートを表示する方法については、次を参照してください。 [SAP に関するレポートを表示](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)です。  
  
## <a name="see-also"></a>参照  
 [SSRS と SAP 用データ プロバイダーを使用します。](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)