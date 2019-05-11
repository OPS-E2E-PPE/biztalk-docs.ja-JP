---
title: ENTSSO MA 用に MIIS を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7820384-ff64-4628-9e35-02b13803928f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e536e44ec6c76ba3bf44b346fd6b44e54c3f05b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341295"
---
# <a name="how-to-configure-miis-for-entsso-ma"></a>ENTSSO MA 用に MIIS を構成する方法
Microsoft Identity Integration Server (MIIS) を実行するコンピューターでエンタープライズ シングル サインオン (SSO) 管理機能 (完全なバージョンまたは管理ツールのみのバージョン) をインストールするときに、ENTSSO 管理エージェントは自動的にインストールします。 つまり、MIIS を起動するときにほぼすべての構成が既に実行されています。 接続情報は、一部が不足しているだけです。  
  
 この手順を開始する前に、次の情報を確認してください。  
  
-   ENTSSO サーバーの名前。  
  
-   ユーザー Id とする ENTSSO 管理エージェントは、SSO サーバーと通信する Windows アカウントのパスワード。  
  
### <a name="to-configure-the-management-agent-within-miis"></a>MIIS で管理エージェントを構成するには  
  
1.  MIIS を開き、開く、 **Identity Manager**します。  
  
2.  開く、**管理エージェントを作成** ダイアログ ボックス。  
  
3.  選択**エンタープライズ シングル サインオン**一覧にします。  
  
     起動、**管理エージェント作成ウィザード**します。  
  
4.  **接続情報の構成**ページで、**接続先:** フィールドに、SSO サーバーの名前を入力します。  
  
5.  ENTSSO 管理エージェントの名前を入力します。 この名前は、ENTSSO.xml ファイルで指定された名前と一致する必要があります。  
  
6.  **ユーザー**フィールドに、ENTSSO 管理エージェントを使用して、SSO データベース内のマッピングを管理するドメイン アカウントを指定します。  
  
     このアカウントは、いずれか、SSO システム内の SSO 関連管理者または SSO 管理者アカウントのメンバーである必要があります。  
  
7.  **パスワード**フィールドに、そのユーザーのパスワードを入力します。  
  
8.  をクリックして**次**、既定値のままに到達するまで、**拡張機能の構成**ページ。  
  
9. ほぼ**接続情報**パスワード拡張機能をクリックして**設定**します。  
  
     **接続設定** ダイアログ ボックスが表示されます。  
  
10. **接続先**ボックスに、適切なアカウントを入力します。 このアカウントは、指定されたコンピューターで実行されている ENTSSO サービスのサービス アカウントと同じである必要があります。  
  
11. **ユーザー**と**パスワード**フィールドに、アカウントのユーザー名とパスワードを入力します。  
  
12. **[OK]** をクリックします。  
  
13. **MIISCreate 管理エージェント**、 をクリックして**完了**します。  
  
14. **Identity Manager**、クリックして、**ツール** メニューをクリック**オプション**します。  
  
     **オプション** ダイアログ ボックスが表示されます。  
  
15. 選択**メタバース ルールの拡張機能を有効にする**します。  
  
16. **ルール拡張機能の名前フィールド**、入力**Microsoft.EnterpriseSingleSignOn.ManagementAgent.dll**します。  
  
17. クリックして**OK** MIIS を閉じます。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)