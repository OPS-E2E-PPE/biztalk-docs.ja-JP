---
title: 処理前または処理後のスクリプトの送信先を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6d1a7ec9f661a86ff028b1ec364bbd656cbb2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005291"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの送信先を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、処理前または処理後のスクリプトの送信先を変更する方法について説明します。 これは、アプリケーションをインストールするときにスクリプトがコピーされる場所です。 アプリケーションを別の環境に展開するときは、送信先を変更できます。  
  
> [!IMPORTANT]
>  アプリケーションのアンインストール時に実行するスクリプトに、送信先を指定してください。 指定しないと、スクリプトはローカル ファイル システムにコピーされず、したがってアンインストール時に実行されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの展開プロパティを変更するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、変更するスクリプトが含まれる BizTalk グループ、スクリプトが含まれるアプリケーションの順に展開します。  
  
3. をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**変更**します。  
  
4. **先**ファイル名を含めて、先の場所の完全なパスを入力し、クリックして**OK**します。 アプリケーションのインストール フォルダーを指定するには、パスで環境変数 %BTAD_InstallDir% を使用します。  
  
## <a name="see-also"></a>参照  
 [処理前および処理後のスクリプトの管理](../core/managing-pre-and-post-processing-scripts.md)