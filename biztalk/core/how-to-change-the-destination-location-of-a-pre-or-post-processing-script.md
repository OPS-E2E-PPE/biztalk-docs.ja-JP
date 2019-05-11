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
ms.openlocfilehash: b276b9527371b170f15bfed212470ea52bb98eb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387027"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの送信先を変更する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、前または処理後のスクリプトの送信先を変更する方法について説明します。 これは、アプリケーションがインストールされている場合に、スクリプトをコピーする場所です。 別の環境にアプリケーションをデプロイするときに、先の場所を変更する可能性があります。  
  
> [!IMPORTANT]
>  アプリケーションのアンインストール時に実行するスクリプトの保存先を指定してください。 そうでない場合、スクリプトは、ローカル ファイル システムにはコピーされず、そのため、アンインストール中には実行されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>処理前または処理後のスクリプトの展開プロパティを変更するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を変更するスクリプトが含まれる BizTalk グループを展開し、スクリプトが含まれるアプリケーションを展開します。  
  
3. をクリックして、**リソース**フォルダーは、スクリプトを右クリックし、順にクリックします**変更**します。  
  
4. **先**ファイル名を含めて、先の場所の完全なパスを入力し、クリックして**OK**します。 (を使用できます、環境変数 %btad_installdir% パスでアプリケーションのインストール フォルダーを指定するのに)。  
  
## <a name="see-also"></a>参照  
 [処理前および処理後のスクリプトの管理](../core/managing-pre-and-post-processing-scripts.md)