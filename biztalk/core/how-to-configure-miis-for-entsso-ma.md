---
title: "ENTSSO MA 用に MIIS を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 969a52beb02c3d2ba237369c16efec9ee84e2ef1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-miis-for-entsso-ma"></a>ENTSSO MA 用に MIIS を構成する方法
Microsoft Identity Integration Server (MIIS) を実行しているコンピュータにエンタープライズ シングル サインオン (SSO) の管理機能 (完全なバージョンまたは管理機能のみのバージョン) をインストールすると、ENTSSO 管理エージェントが自動的にインストールされます。 これにより、MIIS を起動するときには、ほとんどすべての構成が既に実行されていることになります。 構成が行われていないのは、接続情報だけです。  
  
 ここで説明する手順を開始する前に、次の情報を準備してください。  
  
-   ENTSSO サーバー名  
  
-   Windows アカウントのユーザー ID とパスワード (ENTSSO 管理エージェントが SSO サーバーとの通信に使用するもの)  
  
### <a name="to-configure-the-management-agent-within-miis"></a>MIIS で管理エージェントを構成するには  
  
1.  MIIS を開き、 **Identity Manager**です。  
  
2.  開く、**管理エージェントを作成する** ダイアログ ボックス。  
  
3.  選択**エンタープライズ シングル サインオン**一覧にします。  
  
     起動、**管理エージェント作成ウィザード**です。  
  
4.  **接続情報の構成**] ページの [、**接続先:**フィールドに、SSO サーバーの名前を入力します。  
  
5.  ENTSSO 管理エージェントの名前を入力します。 この名前は、ENTSSO.xml ファイルで指定されている名前と一致する必要があります。  
  
6.  **ユーザー**フィールドに、ENTSSO 管理エージェントを使用して、SSO データベース内のマッピングを管理するドメイン アカウントを指定します。  
  
     このアカウントは、SSO システム内の SSO 関連管理者アカウントまたは SSO 管理者アカウントのメンバであることが必要です。  
  
7.  **パスワード**フィールドに、そのユーザーのパスワードを入力します。  
  
8.  をクリックして**[次へ]**、既定値のままに到達するまで、**拡張機能の構成**ページ。  
  
9. 近く**接続情報**パスワード拡張機能をクリックして**設定**です。  
  
     **接続設定** ダイアログ ボックスが表示されます。  
  
10. **Connect To**ボックスに、適切なアカウントを入力します。 このアカウントは、指定したコンピュータ上で実行している ENTSSO サービスのサービス アカウントと同じであることが必要です。  
  
11. **ユーザー**と**パスワード**フィールドに、アカウントのユーザー名とパスワードを入力します。  
  
12. **[OK]**をクリックします。  
  
13. **MIISCreate 管理エージェント**をクリックして**完了**です。  
  
14. **Identity Manager**をクリックして、**ツール** メニューをクリックして**オプション**です。  
  
     **オプション** ダイアログ ボックスが表示されます。  
  
15. 選択**メタバース ルールの拡張機能を有効にする**です。  
  
16. **ルール拡張機能の名前フィールド**、入力**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**です。  
  
17. をクリックして**OK** MIIS を閉じます。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)