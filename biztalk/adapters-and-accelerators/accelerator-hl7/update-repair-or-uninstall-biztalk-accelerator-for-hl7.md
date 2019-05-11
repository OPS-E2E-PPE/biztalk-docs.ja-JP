---
title: 更新、修復、または for HL7 の BizTalk アクセラレータのアンインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2fc84d2-1262-4a6e-ae9c-488a00ab4099
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d9ab8aa171c814ed353e289911c31e8c08fcb11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286415"
---
# <a name="update-repair-or-uninstall-biztalk-accelerator-for-hl7"></a>更新、修復、または for HL7 の BizTalk アクセラレータのアンインストール

変更、修復、アンインストール、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]します。  
  
> [!IMPORTANT]
>  アンインストールすることを確認する[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] 場合はアンインストールできません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]はインストールされません。  

## <a name="prerequisites"></a>前提条件
* メンバーであるアカウントを使用してサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

* このユーザー アカウントを Administrators グループのメンバーがあります、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk Accelerator for HL7 のデータを格納します。  
    
## <a name="update-an-existing-installation"></a>更新プログラムの既存のインストール

> [!NOTE]
>  インストールを変更するときに[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]、エンド ツー エンドのチュートリアルは自動的に実行されません。 
> 
> チュートリアルを実行し、変更後のインストールが正しく実行されることを確認します実行から手動でチュートリアル、 ***\<ドライブ\>*** **\Program Files\Microsoft BizTalk \< 。バージョン\>HL7\SDK\End ツー エンドのチュートリアルのアクセラレータ**フォルダー。
  
1. 実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**に管理者として 
  
2. [ようこそ] ページで、次のように選択します。**次**します。  
  
3. **プログラムのメンテナンス**を選択します**変更**、し、**次**します。  
  
4. **カスタム セットアップ**をインストールする機能を選択して、チェック ボックスをオフの機能はありませんしを選択し、**次**します。  
  
5. 概要では、次のように選択します。**次**します。  
  
6. **[インストール]** を選択します。  
  
7. 完了すると、選択**完了**します。  

## <a name="repair-an-existing-installation"></a>既存のインストールを修復します。
[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]ウィザードが見つからないか壊れているファイル、ショートカット、またはレジストリ エントリを修正して、インストールを修復します。  
  
1. 実行、 [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] **setup.exe**管理者として。  
  
2. [ようこそ] ページで、次のように選択します。**次**します。  
  
3. **プログラムのメンテナンス**を選択します**修復**、し、**次**します。  
  
4. **サービス アカウントのログ記録**、ユーザー アカウントを再入力し、 **OK**します。  
  
5. メッセージが表示されたら**アカウント名が許可されているログオン適切なサービスとして**を選択し、 **OK**を続行します。  
  
6. 修復する準備が完了したら、選択**インストール**します。  
  
7. 完了したら、選択**完了**します。 

  
## <a name="uninstall-btahl7"></a>BTAHL7 をアンインストールします。  

> [!IMPORTANT]
>  ある場合、受信場所または送信ポートの MLLP トランスポートの種類を使用して、BTAHL7 セットアップの BTAHL7 のアンインストール時に MLLP アダプターは削除されません。 アンインストールする前に削除のすべての受信場所または送信ポートの MLLP トランスポートを使用しています。 または、別の型 MLLP からトランスポートの種類を変更します。 次に、アンインストール、MLLP アダプターが削除されます。  
      
1. 開いている**プログラムと機能**します。  
  
2. 選択[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]、し、**アンインストール**します。  
  
3. 選択**はい**ことを確認するように求められる場合。 
  
4. 完了したら、選択**完了**します。  
  
   > [!NOTE]
   >  BTAHL7 が自動的にアンインストールされない[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アイテムとアセンブリです。  
  

  
## <a name="troubleshooting-installation-issues"></a>インストールに関する問題のトラブルシューティング  
 かどうか、サーバーでは、ユーザーがいるかどうかを検証できない、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者は、BTAHL7 をアンインストールする、次のエラーを返します。 
 
 `Fatal error during uninstallation`  
  
アンインストールを続行するには、次の操作を行います。  
  
1. ローカル管理者としてサーバーにサインインします。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] をアンインストールします。  
  
3. [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] をアンインストールします。  
  
## <a name="see-also"></a>参照  
[Microsoft BizTalk Accelerator for HL7 のインストールまたはアップグレード](../../adapters-and-accelerators/accelerator-hl7/install-or-upgrade-microsoft-biztalk-accelerator-for-hl7.md)