---
title: インポートおよびエクスポートの BizTalk Server の構成 |Microsoft Docs
description: 手順を適用するには、インポート、エクスポートまたは、コンポーネントの構成を解除およびデータベースと BizTalk Server のサービス アカウントを更新
ms.custom: ''
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6206ed8-d087-44cc-8ab5-da5d8a28e09a
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60faef2bf700a5e7fa1f5ced556e9fdd572201b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980739"
---
# <a name="import-and-export-biztalk-server-configuration"></a>BizTalk Server 構成のインポートとエクスポート
BizTalk Server 構成では、ローカル コンピューターにインストールした機能の構成状態に関する包括的な分析が提供されます。 このツールを使用すると、機能の構成と構成解除、セキュリティ設定の構成、および構成のインポートとエクスポートを行えます。  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>BizTalk Server の構成を使用する前提条件  
   
-   としてサインインしているアカウントは、ローカルの administrators グループのメンバーであるし、SQL Server のシステム管理者権限を持っている必要があります。  
  
-   BizTalk Server によって生成され、BizTalk Server 構成で一覧表示される既定のアカウントは、ローカル グループに属しています。 マルチ サーバー環境では、これらのローカル グループにドメイン グループを置き換えます。  
  
-   サインインしているアカウントを構成する場合、OLAP コンピューターでは、OLAP 管理者グループのメンバーにすることがあります。  
  
    > [!NOTE]
    >  現在サインインしているユーザーのグループ メンバーシップを変更すると、グループは、ドメインのメンバーでも、out、ことを確認して署名して、変更が完了した後にもう一度、サインインします。 署名しない場合の出力/記号にすることがありますのアクセスを拒否、現在のログインが新しいグループのメンバーシップを反映できません。  
  
## <a name="apply-the-configuration"></a>構成を適用します。  
  
1.  **[BizTalk Server 構成]** で、**[構成の適用]** をクリックします。  
  
2.  **[概要]** 画面で、構成を確認して **[次へ]** をクリックします。  
  
3.  **[完了]** 画面で、**[完了]** をクリックします。  
  
## <a name="import-configuration"></a>構成のインポート

> [!IMPORTANT]
> 構成ファイルをインポートすると、構成ファイルが BizTalk Server を構成するにはインストールされていませんのコンポーネントを構成していないことを確認します。 BizTalk Server 上にインストールされていないコンポーネントを構成しようとすると、デッドロック状態が発生することがあります。 このような状況では、構成ファイルで構成しようとするコンポーネントに依存するコンポーネントの構成を解除します。 ただし、依存コンポーネントの構成を解除しようとしています。 には、不足しているコンポーネントが存在し構成する必要があります。 この問題を解決するには、アンインストールのコンポーネントへの参照を削除する構成ファイルを編集または構成ファイルを BizTalk Server の互換性のあるインストールに適用する必要があります。  
> 
>  パスワードとバックアップ ファイルの場所は、インポートするファイルを手動で編集していない限り、構成ファイルでは保存されません。 機能が既に構成はインポートされません。  
  
  
1.  **[BizTalk Server 構成]** で、**[構成のインポート]** をクリックします。  
  
2.  **[開く]** ダイアログ ボックスで、インポートする構成ファイルを選択し、**[開く]** をクリックします。  
  
3.  **[BizTalk Server 構成]** で、**[構成の適用]** をクリックします。  
  
4.  **[概要]** 画面で、構成を確認して **[次へ]** をクリックします。  
  
5.  **[完了]** 画面で、**[完了]** をクリックします。  

BizTalk Server 構成フレームワークを使用して BizTalk Server 構成ファイルをインポートすることができます。 これらのファイルを使用した作業の詳細については、「[構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md)」を参照してください。  
  
## <a name="export-configuration"></a>エクスポートの構成

> [!NOTE]
>  構成ファイルには、パスワードが保存されていません。    
 
1. **[BizTalk Server 構成]** で、**[構成のエクスポート]** をクリックします。  
  
2. **[名前を付けて保存]** ダイアログ ボックスで、保存するファイル名を入力し、**[保存]** をクリックします。  

   BizTalk Server 構成フレームワークを使用して BizTalk Server の構成をエクスポートすることができます。 これらのファイルの使用方法の詳細については、次を参照してください[構成フレームワークを使用。](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
## <a name="unconfigure-features"></a>機能の構成解除  
 コンピューター上の BizTalk Server 機能の構成を解除するには、BizTalk Server 構成で機能を削除します。  
  
> [!NOTE]
>  機能の構成を解除する前に、BizTalk Server 管理コンソールを閉じる必要があります。  
  
 
1.  **[BizTalk Server 構成]** で、**[機能の構成解除]** をクリックします。  
  
2.  **[機能の構成解除]** ダイアログ ボックスで、削除する機能を選択し、**[OK]** をクリックします。  
  
    > [!NOTE]
    >  選択した機能の構成を解除しようとしていることを示す警告が表示されます。 **[はい]** をクリックして続行します。  
  
3.  **[概要]** 画面で、構成を確認して **[次へ]** をクリックします。  
  
4.  **[完了]** 画面で、**[完了]** をクリックします。  
  
## <a name="update-databases"></a>データベースを更新します。  
 BizTalk Server 機能に関連付けられたデータベース サーバーとデータベースを変更するには、BizTalk Server 構成でデータベース サーバーとデータベースを編集します。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の構成では、SQL Servedr の既定のインスタンスと名前付きインスタンスがサポートされます。  
> 
>  このツールでは、データベースを一括して編集できます。  
  
 
1.  **[BizTalk Server 構成]** で、**[表示]** をクリックし、**[データベース]** をクリックします。  
  
2.  **[データベース]** ダイアログ ボックスで、編集する機能を選択し、**[編集]** をクリックします。  
  
3.  **[データベース]** ダイアログ ボックスで、使用するデータベース サーバー名とデータベース名を入力し、**[OK]** をクリックします。  
  
4.  **[データベース]** ダイアログ ボックスで **[閉じる]** をクリックします。  
  
## <a name="update-service-accounts"></a>サービス アカウントを更新します。  
 BizTalk Server 機能に関連付けられたサービス アカウントを変更するには、BizTalk Server 構成でデータベース サーバーとデータベースを編集します。  
  
> [!NOTE]
>  このツールでは、アカウントを一括で編集できます。  
  
1.  **[BizTalk Server 構成]** で、**[表示]** をクリックし、**[サービス アカウント]** をクリックします。  
  
2.  **[サービス アカウント]** ダイアログ ボックスで、編集する機能を選択し、**[編集]** をクリックします。  
  
3.  **[ユーザーの資格情報]** ダイアログ ボックスで、使用するユーザー名とパスワードを入力し、**[OK]** をクリックします。  
  
4.  **[サービス アカウント]** ダイアログ ボックスで **[閉じる]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)   
 [構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md)   