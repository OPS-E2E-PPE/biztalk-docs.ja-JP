---
title: Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f57155b386af979f1da52d39d062aff171203b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008211"
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a>Data Provider for SAP を使用して、レポート サーバー プロジェクトを作成するには
レポート サーバーを作成する必要がありますを使用して、プロジェクト、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]、SAP システムで使用可能なデータのレポートを生成します。 このトピックでは、レポート サーバー プロジェクトを作成する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明する手順を実行する前にインストールされていることを確認します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]のインストール中に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールします。 詳細については[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]のインストールで使用可能なインストール ガイドを参照してください\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents します。  
  
### <a name="to-create-a-report-server-project"></a>レポート サーバー プロジェクトを作成するには  
  
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]レポート サーバー プロジェクトを作成します。 レポート サーバー プロジェクトを作成するには、次の操作を行います。  
  
   1.  をクリックして、**ファイル** メニューのをクリックして**新規**、 をクリックし、**プロジェクト**します。  
  
   2.  **新しいプロジェクト**] ダイアログ ボックスから、**プロジェクトの種類**一覧で、[**ビジネス インテリジェンス プロジェクト**します。 **Visual Studio にインストールされたテンプレート**一覧で、**レポート サーバー プロジェクト**します。  
  
   3.  プロジェクトの場所と名前を指定し、クリックして**OK**します。 このトピックでは、プロジェクトの名前を指定`SAP_ Report`します。  
  
2. 新しいデータ ソースを追加します。  
  
   1. ソリューション エクスプ ローラーで、右クリックして**共有データ ソース**、 をクリック**新しいデータ ソースの追加**します。  
  
   2. **共有データ ソース** ダイアログ ボックスで、**全般** タブで、データ ソースの名前を指定します。 このトピックと名前を指定`SAPDataSource`します。  
  
   3. **型**一覧で、 **Data Provider for SAP**します。  
  
   4. **接続文字列**ボックスでの接続文字列を指定します、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]します。 については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]接続文字列を参照してください[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
       ![データ ソースを作成する](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")  
  
      > [!NOTE]
      >  接続文字列の一部として、資格情報を指定するか、次の手順」の説明に従って、それらを指定することができます。  
  
   5. **資格情報**タブに、次のいずれかを選択してクリックして**OK**:  
  
      |プロパティ|目的|  
      |--------------|----------------|  
      |**[特定のユーザー名とパスワードを使用する]**|ユーザー名と SAP システムに接続するためのパスワードを指定します。|  
      |**資格情報のプロンプト**|レポートの生成時に、SAP システムの資格情報を入力します。 **注:** の接続文字列の一部として、指定した場合、このオプションは、資格情報をオーバーライドを指定する資格情報。|  
      |**資格情報なし**|接続文字列の一部として、ユーザー名とパスワードを指定する場合は、このオプションを選択します。|  
  
      > [!NOTE]
      >  レポート サーバー プロジェクトの Windows 認証モードはサポートされていません。  
  
3. 新しいレポートを追加します。  
  
   1. ソリューション エクスプ ローラーで、右クリックして**レポート**、 をクリックし、**新しいレポートの追加**します。  
  
       これは、レポート ウィザードを起動します。  
  
   2. クリックして、ようこそ画面の情報を読み取る**次**します。  
  
   3. **データ ソースを選択** ダイアログ ボックスで、選択、**共有データ ソース**オプションで、選択、 **SAPDataSource**前の手順で作成し、 をクリックして**次へ**します。  
  
   4. 選択した場合、**資格情報の入力を求める**、データ ソースを作成するときにユーザーの資格情報を指定するオプション、**データ ソースの資格情報の入力** ダイアログ ボックスが表示されます。 ユーザー名と、SAP システムに接続し、をクリックし、パスワードを指定**OK**します。  
  
       他の資格情報を指定するためのオプションを選択した場合、ウィザードは、次の手順に進みます。  
  
   5. **クエリをデザインする** ダイアログ ボックスで、レポートを生成するために使用するクエリ文字列を指定します。 以下に例を示します。  
  
      ```  
      SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
      ```  
  
       このクエリでは、NAME1 はするが、レポートの生成中に指定する名前 KNA1 テーブルから上位 2 つのレコードが取得されます。  
  
       **[次へ]** をクリックします。  
  
   6. 以降のダイアログ ボックスでは、レポートを表示する形式を設計できます。 既定の形式を使用する場合をクリックして**完了 >>&#124;** に直接移動する、**完了** ダイアログ ボックス。  
  
   7. **ウィザードの完了**ダイアログ ボックスで、レポートの名前を指定の概要を確認 をクリックし、**完了**します。 このトピックでは、レポートの名前を指定します`SAPReport`します。  
  
      レポートを表示できるようになりました。 レポートを表示する方法については、[SAP についてレポートを表示](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [Data Provider for SAP を SSRS と一緒に使用する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)