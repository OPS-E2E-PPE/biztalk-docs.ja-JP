---
title: LOBWebApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9120d9078303092740fdbfc27b6932b7849cc6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002107"
---
# <a name="lobwebapplication"></a>LOBWebApplication
LOBWebApplication ユーティリティは、実際の基幹業務 (LOB) Web アプリケーションをシミュレートして、ASPX ページから取引先にアクションまたは応答メッセージを送信するために使用します。  
  
 ASPX ページをセットアップした後、ページを起動してメッセージのパラメーター (ホーム組織と取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリ) を入力します。 その後、サービス コンテンツを変更してメッセージを送信できます。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files (86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a>LOBWebApplication 用の仮想サーバーの追加  
  
#### <a name="to-add-a-virtual-server"></a>仮想サーバーを追加するには  
  
1.  クリックして**開始**、 をポイント**シリアルキー**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  インフォメーション サービス マネージャーで、展開**\<コンピューター名\>(ローカル コンピューター)**、展開**Web サイト**、右クリックし、**既定の Web サイト**.  
  
3.  をポイント**新規**、 をクリックし、**仮想ディレクトリ**します。  
  
4.  **仮想ディレクトリの作成ウィザード**] ページで [**次**など、サイトのエイリアスを入力し、 **LOBWebApplication**。  
  
5.  **Web サイトのコンテンツ ディレクトリ** ページで **参照**に移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk \<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication、 をクリックして**OK**、順にクリックします**次**します。  
  
6.  **仮想ディレクトリのアクセス許可**] ページで、[**読み取り**と**スクリプトを実行する**、順にクリックします**次**。 **[完了]** をクリックします。  
  
7.  BTARN を構成するために使用するサービス アカウント ユーザー (hostsvc など) を STS_WPG に追加します。  
  
8.  C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files にあるファイルをすべて削除します。 ファイルを削除する前に、iisreset プログラムを実行してファイルのロックを解除する必要がある場合があります。  
  
9. IIS マネージャーで、アプリケーション プール BTARNHTTPReceivePool の下で実行するように LOBWebApplication を設定します。  
  
10. IIS マネージャーを使用して、LOBWebApplication ユーティリティの [Directory Security Properties] セクションで、仮想ディレクトリを匿名で実行するオプションを無効にします。  
  
## <a name="building-lobwebapplication"></a>LOBWebApplication の構築  
  
#### <a name="to-build-lobwebapplication"></a>LOBWebApplication を構築するには  
  
1. Visual Studio を起動します。  
  
2. **ファイル**、 をポイント**オープン**、 をクリックし、**ソリューションを開く**。  
  
3. 移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobwebapplication には、選択**LOBWebApplication.sln**、 をクリックし、**オープン**します。  
  
   > [!NOTE]
   >  LOBWebApplication 用の仮想サーバーを追加していない場合、ソリューションは [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で正常に開きません。  
  
4. 右クリック**参照**、 をクリックし、**参照の追加**します。  
  
5. **参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動\<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk \<バージョン\>Accelerator for rosettanet \bin が、Microsoft.Solutions.BTARN.ConfigurationManager.dll および Microsoft.Solutions.BTARN.Shared.dll ファイルを選択し、クリックして**オープン**します。  
  
6. 右クリック**LOBWebApplication**、 をクリックし、**ビルド**します。  
  
## <a name="running-lobwebapplication"></a>LOBWebApplication の実行  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a>LOBWebApplication を実行してメッセージを送信するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、順にクリックします**Internet Explorer**します。  
  
2.  Internet Explorer で、**アドレス**ボックスに「 http://localhost/LOBWebApplication、 をクリックし、**移動**します。  
  
3.  **Submit Message**  ダイアログ ボックスに、ホーム組織、取引先組織、PIP コード、PIP バージョン、PIP インスタンス ID、およびメッセージ カテゴリを入力します。  
  
4.  必要に応じてサービス コンテンツを変更します。  
  
5.  **[送信]** をクリックします。  
  
## <a name="remarks"></a>コメント  
 LOBWebApplication ユーティリティは、指定した PIP からメッセージのインスタンスを生成し、ASPX ページに生成されたメッセージのインスタンスからサービスのコンテンツを入力します。 この処理を実行する際、LOBWebApplication ユーティリティは、書式設定されたメッセージ インスタンスを PIP から直接生成するのと同じ技法を使用します。 詳細については、次を参照してください。 [PIP からの整形式メッセージ インスタンスを作成する](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)します。 ASPX ページのサービス コンテンツのフィールドに実際のデータを入力すると、実際のメッセージ インスタンスを生成できます。  
  
 LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。 LOBApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) デスクトップ アプリケーションをシミュレートするために使用します。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
