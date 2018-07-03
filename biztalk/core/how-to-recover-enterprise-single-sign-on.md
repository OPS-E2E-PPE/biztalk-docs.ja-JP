---
title: エンタープライズ シングル サインオンを復旧する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 845e6ff7-88a8-4ab4-b307-f9275d44600e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d56953fcab29b53f23ba3097296a74aeb67a17c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973123"
---
# <a name="how-to-recover-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンを復旧する方法
BizTalk Server を復旧する前に、まずはエンタープライズ シングル サインオン (SSO) を復旧する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
-   この作業を実行するには、シングル サインオン管理者グループのメンバーおよび管理者グループのメンバーとしてログオンする必要があります。  
  
-   SSO の構成中に使用したパスワードが必要です。  
  
-   リモート サーバー上のすべてのデータベースが破損していない必要があります。  
  
-   バックアップ マスター シークレット ファイルが破損しておらず、安全な場所に格納されている必要があります。  
  
### <a name="to-recover-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンを復旧するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。  
  
2. Microsoft BizTalk Server 構成では、コンソール ツリーで、クリックして**エンタープライズ SSO**します。  
  
3. 詳細] ウィンドウで、[**を有効にするエンタープライズ シングル サインオン コンピューターこの**、順にクリックします**既存の SSO システムに参加**します。  
  
4. **データ ストア**、SSO データベースと SSO データベースの名前をホストする SQL server の名前を入力します。  
  
5. **Windows サービス**、最初にインストールして BizTalk Server を構成するときに使用した SSO サービス アカウントのユーザー名とパスワードを入力します。  
  
   > [!NOTE]
   >  別のアカウントを使用することもできますが、使用するアカウントはシングル サインオン管理者グループのメンバーである必要があります。  
  
6. **[構成の適用]** をクリックします。  
  
    マスター シークレットが取得されなかったことを示す警告が表示されます。 イベント ビューアーを使用すると、エンタープライズ シングル サインオン サービスがコンピューターで開始され実行されていることを確認できます。  
  
7. クリックして**ファイル**、 をクリックし、**終了**します。  
  
8. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
9. コマンド プロンプトで、次のように入力します。  
  
     **cd Program files \common files \enterprise でシングル サインオン**  
  
10. コマンド プロンプトで、次のように入力します。  
  
     **ssoconfig-restoresecret***\<backupfile  \>*  
  
     場所*\<backupfile\>* バックアップしたマスター シークレット ファイルの名前を指定します。  
  
     ときに**ssoconfig** SSO を構成中に指定されたパスワードを入力するバックアップ ファイルのパスワードをユーザーに求めます。 パスワードが正しい場合、 **ssoconfig**次のメッセージが表示されます。  
  
     **操作は正常に完了しました**  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)   
 [Enterprise を構成する BizTalk Server 構成を使用して SSO](http://msdn.microsoft.com/library/f63d1aec-a8c7-4e76-a67f-19af69e252f0)