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
ms.openlocfilehash: 8677b05f06d54d61b07b8157bb425fb83c6d4c8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266187"
---
# <a name="import-and-export-biztalk-server-configuration"></a>インポートおよびエクスポートの BizTalk Server の構成
BizTalk Server の構成では、ローカル コンピューターにインストールした機能の構成状態に関する高度な分析を提供します。 このツールを使用すると、構成し機能の構成解除、セキュリティの設定を構成し、インポートおよび構成をエクスポートできます。  
  
## <a name="prerequisites-to-use-the-biztalk-server-configuration"></a>BizTalk Server の構成を使用する前提条件  
   
-   としてサインインしているアカウントは、ローカルの administrators グループのメンバーであるし、SQL Server のシステム管理者権限を持っている必要があります。  
  
-   BizTalk Server によって生成され、BizTalk Server 構成で一覧表示の既定のアカウントは、ローカル グループです。 マルチ サーバー環境では、これらのローカル グループにドメイン グループを置き換えます。  
  
-   サインインしているアカウントを構成する場合、OLAP コンピューターでは、OLAP 管理者グループのメンバーにすることがあります。  
  
    > [!NOTE]
    >  現在サインインしているユーザーのグループ メンバーシップを変更すると、グループは、ドメインのメンバーでも、out、ことを確認して署名して、変更が完了した後にもう一度、サインインします。 署名しない場合の出力/記号にすることがありますのアクセスを拒否、現在のログインが新しいグループのメンバーシップを反映できません。  
  
## <a name="apply-the-configuration"></a>構成を適用します。  
  
1.  **BizTalk Server 構成**、 をクリックして**構成の適用**します。  
  
2.  **概要**画面で、構成を順にクリックします**次**します。  
  
3.  **完了**画面で、**完了**します。  
  
## <a name="import-configuration"></a>構成のインポート

> [!IMPORTANT]
> 構成ファイルをインポートすると、構成ファイルが BizTalk Server を構成するにはインストールされていませんのコンポーネントを構成していないことを確認します。 BizTalk Server に存在しないコンポーネントを構成しようとは、デッドロック状態が発生する可能性があります。 このような状況では、構成ファイルで構成しようとするコンポーネントに依存するコンポーネントの構成を解除します。 ただし、依存コンポーネントの構成を解除しようとしています。 には、不足しているコンポーネントが存在し構成する必要があります。 この問題を解決するには、アンインストールのコンポーネントへの参照を削除する構成ファイルを編集または構成ファイルを BizTalk Server の互換性のあるインストールに適用する必要があります。  
> 
>  パスワードとバックアップ ファイルの場所は、インポートするファイルを手動で編集していない限り、構成ファイルでは保存されません。 機能が既に構成はインポートされません。  
  
  
1.  **BizTalk Server 構成**、 をクリックして**構成のインポート**します。  
  
2.  **オープン**ダイアログ ボックスで、構成ファイルをクリックして、インポートする**オープン**します。  
  
3.  **BizTalk Server 構成**、 をクリックして**構成の適用**します。  
  
4.  **概要**画面で、構成を順にクリックします**次**します。  
  
5.  **完了**画面で、**完了**します。  

BizTalk Server 構成フレームワークを使用して BizTalk Server 構成ファイルをインポートすることができます。 これらのファイルの使用方法の詳細については、次を参照してください。[構成フレームワークを使用](../install-and-config-guides/working-with-the-configuration-framework.md)します。  
  
## <a name="export-configuration"></a>エクスポートの構成

> [!NOTE]
>  パスワードは、構成ファイルに保存されません。    
 
1. **BizTalk Server 構成**、 をクリックして**構成のエクスポート**します。  
  
2. **付けて**ダイアログ ボックスで、クリックして、保存するファイル名を入力**保存**します。  

   BizTalk Server 構成フレームワークを使用して BizTalk Server の構成をエクスポートすることができます。 これらのファイルの使用方法の詳細については、次を参照してください[構成フレームワークを使用。](../install-and-config-guides/working-with-the-configuration-framework.md)  
  
## <a name="unconfigure-features"></a>機能の構成解除します。  
 コンピューター上の BizTalk Server 機能の構成を解除するには、BizTalk Server の構成で削除します。  
  
> [!NOTE]
>  機能の構成解除する前に、BizTalk Server 管理コンソールを終了する必要があります。  
  
 
1.  **BizTalk Server 構成**、 をクリックして**機能の構成解除**します。  
  
2.  **機能の構成解除**ダイアログ ボックスで、削除する機能の選択とクリック**OK**します。  
  
    > [!NOTE]
    >  選択した機能の構成を解除しようとしていることを警告するダイアログ ボックスが表示されます。 **[はい]** をクリックして続行します。  
  
3.  **概要**画面で、構成を順にクリックします**次**します。  
  
4.  **完了**画面で、**完了**します。  
  
## <a name="update-databases"></a>データベースを更新します。  
 データベース サーバーと、BizTalk Server 構成で編集することにより、BizTalk Server の機能に関連付けられているデータベースを変更することができます。  
  
> [!NOTE]
>  構成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インスタンスと名前付きインスタンスのサポートに対する SQL Server の既定値。  
> 
>  このツールは、データベースの編集を一括でできます。  
  
 
1.  **BizTalk Server 構成**、 をクリックして**ビュー**、 をクリックし、**データベース。**  
  
2.  **データベース** ダイアログ ボックス、編集する機能を選択およびクリック**編集**します。  
  
3.  **データベース**ダイアログ ボックスで、データベース サーバー名とデータベース名をクリックして、使用する型**OK**します。  
  
4.  **データベース**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
## <a name="update-service-accounts"></a>サービス アカウントを更新します。  
 BizTalk Server の構成で編集することにより、BizTalk Server の機能に関連付けられているサービス アカウントを変更することができます。  
  
> [!NOTE]
>  このツールは、一括編集するアカウントを使用できます。  
  
1.  **BizTalk Server 構成**、 をクリックして**ビュー**、 をクリックし、**サービス アカウント**します。  
  
2.  **サービス アカウント** ダイアログ ボックス、編集する機能を選択およびクリック**編集**します。  
  
3.  **ユーザーの資格情報** ダイアログ ボックスで、ユーザー名とパスワードを使用して、クリックする入力**OK**。  
  
4.  **サービス アカウント**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)   
 [構成フレームワークを使用](../install-and-config-guides/working-with-the-configuration-framework.md)   