---
title: "更新、修復、または BizTalk Accelerator を HL7 のアンインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb49cdff18e880c91034aaf7d2ab81500c40dbab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a>更新、修復、または BizTalk Accelerator を HL7 のアンインストール

変更、修復、アンインストール、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]です。  
  
> [!IMPORTANT]
>  アンインストールすることを確認する[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]場合はアンインストールできません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]がインストールされていません。  

## <a name="prerequisites"></a>前提条件
* メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

* このユーザー アカウントの Administrators グループのメンバーである必要がありますも、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk Accelerator for HL7 のデータを格納します。  
    
## <a name="update-an-existing-installation"></a>更新プログラムの既存のインストール

> [!NOTE]
>  インストールを変更すると[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]、エンド ツー エンドのチュートリアルは自動的に実行されません。 
> 
> このチュートリアルを実行し、変更後のインストールが正しく実行されることを確認してくださいから手動でチュートリアルを実行、 ***\<ドライブ >*** **\Program Files\Microsoft BizTalk\<バージョン >HL7\SDK\End エンドツー エンド チュートリアルのアクセラレータ**フォルダーです。
  
1. 実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**を管理者として 
  
2.  [ようこそ] ページで、**次**です。  
  
3.  **プログラムのメンテナンス**select、**変更**、し、**次**です。  
  
4.  **カスタム セットアップ**を選択し、必要な機能をインストールする、クリア、機能しないしを選択し、**次**です。  
  
5.  つまり、次のように選択します。**次**です。  
  
6.  **[インストール]**を選択します。  
  
7. 完了したら、**[完了]** を選択します。  

## <a name="repair-an-existing-installation"></a>既存のインストールを修復します。
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]不足または壊れているファイルやショートカット、レジストリ エントリを修正して、インストールを修復します。  
  
1. 実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**管理者として。  
  
2.  [ようこそ] ページで、**次**です。  
  
3.  **プログラムのメンテナンス****修復**、し、**次**。  
  
4.  **サービス アカウントのログ記録**ユーザー アカウントを再入力し、 **OK**です。  
  
4.  メッセージが表示されたら**アカウント名が与えられてログオン右サービスとして**選択してから、 **OK**を続行します。  
  
5.  修復する準備ができたらを選択**インストール**です。  
  
6. 完了すると、選択**完了**です。 

  
## <a name="uninstall-btahl7"></a>BTAHL7 をアンインストールします。  

> [!IMPORTANT]
>  ある場合、受信場所または送信ポートが MLLP のトランスポートの種類を使用して、BTAHL7 セットアップは、BTAHL7 のアンインストール時に MLLP アダプターを削除できません。 アンインストールする前に削除のすべての受信場所または送信ポートの MLLP トランスポートを使用します。 または、別の型に MLLP からトランスポートの種類を変更します。 その後、アンインストール MLLP アダプターが削除されます。  
      
1.  **[プログラムと機能]** を開きます。  
  
2.  選択[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、し、**アンインストール**です。  
  
4.  選択**はい**確認を求められた場合。 
  
5.  完了すると、選択**完了**です。  
  
    > [!NOTE]
    >  BTAHL7 が自動的にアンインストールされない[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アイテムとアセンブリです。  
  

  
## <a name="troubleshooting-installation-issues"></a>インストールに関する問題のトラブルシューティング  
 かどうか、サーバーは、ユーザーがいるかどうかを検証することは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者は、BTAHL7 をアンインストールする、次のエラーを返します。 
 
 `Fatal error during uninstallation`  
  
アンインストールを続行するには、次の操作を行います。  
  
1.  ローカル管理者としてサーバーにサインインします。  
  
2.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。  
  
3.  [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] をアンインストールします。  
  
## <a name="see-also"></a>参照  
[インストールまたは Microsoft BizTalk Accelerator 用 HL7 にアップグレード](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)