---
title: 前または処理後のスクリプトの移行先の場所を変更する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 7eb4ba338790e301e54a9bf262a49808a0a55315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249290"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの送信先を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、処理前または処理後のスクリプトの送信先を変更する方法について説明します。 これは、アプリケーションをインストールするときにスクリプトがコピーされる場所です。 アプリケーションを別の環境に展開するときは、送信先を変更できます。  
  
> [!IMPORTANT]
>  アプリケーションのアンインストール時に実行するスクリプトに、送信先を指定してください。 指定しないと、スクリプトはローカル ファイル システムにコピーされず、したがってアンインストール時に実行されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの展開プロパティを変更するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、変更するスクリプトが含まれる BizTalk グループ、スクリプトが含まれるアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、スクリプトを右クリックし、をクリックして**変更**です。  
  
4.  **先**ファイル名を含む、移行先の場所の完全なパスを入力して、をクリックして**OK**です。 アプリケーションのインストール フォルダーを指定するには、パスで環境変数 %BTAD_InstallDir% を使用します。  
  
## <a name="see-also"></a>参照  
 [前処理および後処理のスクリプトを管理します。](../core/managing-pre-and-post-processing-scripts.md)