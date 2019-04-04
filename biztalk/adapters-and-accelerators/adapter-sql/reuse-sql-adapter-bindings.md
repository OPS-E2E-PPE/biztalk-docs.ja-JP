---
title: SQL アダプターのバインドを再利用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bc8140f-1d40-492c-bce1-b85e992b3567
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6995f62b6dc94734b6e5dac01fad4284e6fcf7fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009987"
---
# <a name="reuse-sql-adapter-bindings"></a>SQL アダプターのバインドを再利用します。
バインド (オーケストレーション ポートやロール リンクの場合) 論理的エンドポイントとの物理的なエンドポイント間のマッピングを作成します (などの送信と受信ポート)。 これにより、BizTalk ビジネス ソリューションの複数のコンポーネント間で通信できるようになります。 バインドを作成するを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="what-is-a-binding-file"></a>バインド ファイルとは何ですか。  
 バインド ファイルは、BizTalk アセンブリ、アプリケーション、またはグループのスコープ内の各 BizTalk オーケストレーションのバインド情報を含む XML ファイルです。 バインド ファイルについて説明します。  
  
- 各オーケストレーションがバインドされているホスト。  
  
- ホストの信頼レベル。  
  
- 各設定は、送信ポート、受信ポート、受信場所、およびパーティが構成されています。  
  
  バインド ファイルを生成し、アセンブリ、アプリケーション、またはグループに含まれているバインドを適用できます。 これにより、異なるデプロイ環境のバインドを手動で構成することによって、アプリケーションの展開を高速化します。  
  
  バインド ファイルは BizTalk アセンブリ、アプリケーション、またはグループを自動的には生成されません。 ただし、バインドをエクスポートすることによって、バインド ファイルを生成できます。 同様をアプリケーションまたはグループにし、バインド ファイルをインポートすることができます。 このセクションでは、インポートしてバインドをエクスポートする方法を説明します。  
  
  バインドおよびバインド ファイルについての詳細については、[バインド ファイルとアプリケーションの展開](../../core/binding-files-and-application-deployment.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
 
## <a name="export-bindings"></a>バインドをエクスポートします。
このセクションでは、XML ファイルに BizTalk アプリケーションのバインドをエクスポートする方法について説明します。 別の BizTalk アプリケーションに XML ファイルからのバインドをインポートできます。 バインドをインポートするには、アプリケーションで同じ名前の既存のバインドが上書きされます。 バインドをアプリケーションに追加して、既存のバインドを上書きしないようにすることもできます。 アプリケーションをインポートしない限り、追加したバインドは有効になりません。  
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. エクスポートするバインドを選択するアプリケーションを右クリックして**エクスポート**、し、**バインド**します。  
  
4. **バインドのエクスポート**] ページの [**ファイルにエクスポート**バインドをエクスポートする XML ファイルの絶対パスを入力します。  
  
    たとえば、入力します `C:\Bindings\Application1Bindings.Binding1.xml`  
  
5. 確認します **、現在のアプリケーションからすべてのバインドをエクスポート**が選択されています。  
  
6. グループのすべてのパーティ情報をエクスポートするには、選択、 **グローバル パーティ情報**チェック ボックスをオンします。  
  
7. **[OK]** を選択します。 バインドは、指定した場所に XML ファイルにエクスポートされます。  

## <a name="import-bindings"></a>バインドのインポート
BizTalk Server 管理コンソールを使用してバインドをインポートします。
  
1. 開く、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. バインドのインポートを選択するアプリケーションを右クリックして**インポート**、し、**バインド**します。  
  
4. バインド ファイルを選択し、**オープン**します。  
  
バインド ファイルのアイテムがアプリケーションに書き込まれます。 これらのアイテムは、アプリケーションの該当するフォルダーに表示されます。 たとえば、送信ポートが バインドの表示の一部としてインポート、**送信ポート**フォルダー。  

## <a name="passwords-are-removed"></a>パスワードは削除されます。  
セキュリティ上の理由により、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 [トランスポートのプロパティ] ダイアログ ボックスでパスワードを構成する、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールの送信ポートまたは受信場所。 

ユーザー名とパスワードを指定する方法の詳細については、[for SQL Server 資格情報で、サインオンの構成](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)を参照してください。
  
## <a name="see-also"></a>参照  
[SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)