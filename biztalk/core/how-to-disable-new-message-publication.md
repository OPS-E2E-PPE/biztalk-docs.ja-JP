---
title: 新しいメッセージの公開を無効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9099ecaa-31ed-4880-a0f6-8dbfaf783f7a
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c850fc4ef38d4da6649082ddf157cc9c87b87fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385175"
---
# <a name="disable-new-message-publication"></a>新しいメッセージの公開を無効にします。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは Windows Management Instrumentation (WMI) を使用すると、新しいメッセージの公開を無効にできます。 メッセージ ボックス データベースで新しいメッセージの受信を停止するには、メッセージ ボックス データベースの新しいメッセージの公開を無効にします。 BizTalk Server 環境によっては、マスター メッセージ ボックス データベースの新しいメッセージの公開を無効にすると、パフォーマンスが向上する場合があります。 新しいメッセージの公開を無効にしても、メッセージ ボックス データベース内の既存のメッセージや処理中のサービス インスタンスには影響しません。  
  
 WMI を使用して、新しいメッセージの公開を無効にする方法については、次を参照してください。、 **MSBTS_MsgBoxSetting.DisableNewMessagePublication プロパティ (WMI)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
> [!IMPORTANT]
>  メッセージ ボックス データベースを削除する前に、新しいメッセージの公開を無効にする必要があります。 メッセージ ボックス データベースを削除する方法の詳細については、次を参照してください。[メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。 メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。  
  
-   BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。  
  
-   データベースが存在するコンピューターの SQL Server 管理者である必要があります。  
  
## <a name="disable-steps"></a>手順を無効にします。
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)][BizTalk グループ]、をクリックして**プラットフォームの設定**、 をクリックし、**メッセージ ボックス**します。  
  
3. 詳細ウィンドウで、無効にするをクリックするメッセージ ボックス データベースを右クリックして**プロパティ**します。  
  
4. **メッセージ ボックスのプロパティ**ダイアログ ボックスで、**新しいメッセージの公開を無効にする**チェック ボックスをオンにし**OK**。  
  
## <a name="see-also"></a>参照  
 [メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md)   
 [メッセージ ボックス データベースを追加します。](../core/how-to-add-a-new-messagebox-database.md)   
 [メッセージ ボックス データベースを削除します。](../core/how-to-delete-a-messagebox-database.md)   
 [メッセージ ボックス データベース](../core/the-messagebox-database.md)