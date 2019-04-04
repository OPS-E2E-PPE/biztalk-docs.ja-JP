---
title: 適用し、追跡プロファイルを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, tracking profiles
- tracking profiles, testing
- tracking profiles, deleting
- testing, tracking profiles
ms.assetid: 77cef14b-c390-4da7-a383-b3abe414a168
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffc3b321647a5861a4b4b3d24251f1ecf013ee09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985027"
---
# <a name="how-to-apply-and-remove-a-tracking-profile"></a>追跡プロファイルを適用および削除する方法
追跡プロファイルを作成または変更したら、そのプロファイルをテスト データベースに適用し、結合テストを行って結果を確認します。 追跡プロファイルは、追跡プロファイル エディター (TPE) から直接適用するか、またはコマンド ラインを使用して適用することができます。  
  
## <a name="prerequisites"></a>前提条件  
 ハード ドライブに保存されている、作成済みの追跡プロファイル。  
  
### <a name="to-apply-the-tracking-profile-from-within-the-tpe"></a>TPE から追跡プロファイルを適用するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**追跡プロファイル エディター**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2. **ファイル** メニューのをクリックして**オープン**します。 適用する .btt ファイルが保存されているハード ドライブの場所に移動します。 クリックして**オープン**を読み込みます。  
  
3. **ツール** メニューのをクリックして**追跡プロファイルの適用**から設定されている管理データベースに .btt ファイルを適用する、**管理データベースの設定**にメニュー項目が、**ツール**メニュー。 結合テストを行って結果を確認します。  
  
4. 追跡プロファイルのテストが正常に完了し、追跡プロファイルを展開できるようになったことを、プロファイルの展開を担当する責任者に通知します。  
  
### <a name="to-apply-the-tracking-profile-from-the-command-line"></a>コマンド ラインから追跡プロファイルを適用するには  
  
-   コマンド プロンプトから、次のコマンドを使用して bttdeploy.exe ツールを実行します (このツールは \Tracking フォルダーにあります)。  
  
    ```  
    bttdeploy.exe <profile name>.btt  
    ```  
  
> [!NOTE]
>  このツールを使用するには、BizTalk 管理者特権が必要です。  
  
> [!NOTE]
>  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
> [!IMPORTANT]
>  展開時には、bttdeploy ツールにより、追跡プロファイルに含まれているアセンブリのバージョンが確認され、展開されているアセンブリのバージョンと照合されます。 追跡プロファイルに含まれているアセンブリが展開されていない場合、bttdeploy ツールはエラーになります。  
  
> [!IMPORTANT]
>  コマンド ラインから追跡プロファイルを適用する場合、bttdeploy ツールでは、構成ウィザードの実行時に指定した BizTalk 管理データベースに追跡プロファイルを適用します。 追跡プロファイル エディターのオプション [管理データベースの設定] で別のデータベースを指定した場合は、その設定が使用されます。 bttdeploy ツールのコマンド ライン オプションとして管理サーバーと管理データベースを指定した場合、コマンド ライン オプションが他の設定をオーバーライドします。 Bttdeploy ツールの使用に関する詳細については、[追跡プロファイルの展開ユーティリティ](../core/tracking-profile-deployment-utility.md)を参照してください。  
  
### <a name="to-remove-a-tracking-profile"></a>追跡プロファイルを削除するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**追跡プロファイル エディター**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2. **ファイル** メニューのをクリックして**オープン**します。 適用する .btt ファイルが保存されているハード ドライブの場所に移動します。 クリックして**オープン**を読み込みます。  
  
3. **ツール** メニューのをクリックして**追跡プロファイルの削除**BizTalk 管理データベースから .btt ファイルに基づいて追跡プロファイルを削除します。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイルの作成](../core/creating-tracking-profiles.md)