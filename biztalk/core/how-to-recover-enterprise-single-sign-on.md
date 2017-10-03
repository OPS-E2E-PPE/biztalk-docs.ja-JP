---
title: "エンタープライズ シングル サインオンを回復する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa0c0b5435e235a07046f311a971a0036dc8346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンを復旧する方法
BizTalk Server を復旧する前に、まずはエンタープライズ シングル サインオン (SSO) を復旧する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   この作業を実行するには、シングル サインオン管理者グループのメンバーおよび管理者グループのメンバーとしてログオンする必要があります。  
  
-   SSO の構成中に使用したパスワードが必要です。  
  
-   リモート サーバー上のすべてのデータベースが破損していない必要があります。  
  
-   バックアップ マスター シークレット ファイルが破損しておらず、安全な場所に格納されている必要があります。  
  
### <a name="to-recover-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンを復旧するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。  
  
2.  Microsoft BizTalk Server 構成で、コンソール ツリーで、をクリックして**エンタープライズ SSO**です。  
  
3.  詳細ウィンドウで、次のように選択します。**を有効にするエンタープライズ シングル サインオンこのコンピューターに**、クリックして**既存の SSO システムに参加**です。  
  
4.  **データ ストア**、SSO データベースと SSO データベースの名前をホストする SQL server の名前を入力します。  
  
5.  **Windows サービス**、最初にインストールして BizTalk Server を構成するときに使用する SSO サービス アカウントのユーザー名とパスワードを入力します。  
  
    > [!NOTE]
    >  別のアカウントを使用することもできますが、使用するアカウントはシングル サインオン管理者グループのメンバーである必要があります。  
  
6.  [**構成の適用**] をクリックします。  
  
     マスター シークレットが取得されなかったことを示す警告が表示されます。 イベント ビューアーを使用すると、エンタープライズ シングル サインオン サービスがコンピューターで開始され実行されていることを確認できます。  
  
7.  をクリックして**ファイル**、クリックして**終了**です。  
  
8.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **cd プログラム files \common files \enterprise でのシングル サインオン**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **ssoconfig restoresecret と入力***\<backupfile >*   
  
     ここで *\<backupfile >*バックアップしたマスター シークレット ファイルの名前を指定します。  
  
     ときに**ssoconfig**バックアップ ファイルのパスワードの入力を求め SSO の構成中に指定されたパスワードを入力してください。 パスワードが正しい場合、 **ssoconfig**次のメッセージが表示されます。  
  
     **操作は正常に完了しました**  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [エンタープライズを構成する BizTalk Server 構成を使用して SSO](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)