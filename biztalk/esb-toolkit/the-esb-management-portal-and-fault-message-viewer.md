---
title: ESB 管理ポータルとエラー メッセージ ビューアー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97b577e280eabece88a9d8196432fb013780c46c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399727"
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a>ESB 管理ポータルとエラー メッセージ ビューアー
主要なコンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は Web ベース ポータルを提供する例外のさまざまな管理とアラートの通知機能は、さらに、便利な構成管理と Universal Description, Discovery, and Integration (機能UDDI) 登録のインターフェイスです。 図 1 は、現在実行中のアプリケーションの正常性の概要を提供すると、ポータルのホーム ページを示します。  
  
 ![ポータルのホーム ページ](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **図 1**  
  
 **ESB 管理ポータルのホーム ページ**  
  
 ユーザーは、図 2 に示すように、エラーのアンビエントと静的のプロパティと、エラー メッセージに含まれる元のメッセージの一覧を表示する、ESB 管理ポータルに表示されるエラー メッセージを選択できます。  
  
 ![[エラー ビューアー] ページ](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4 FaultViewerPage")  
  
 **図 2**  
  
 **ESB 管理ポータルの ESB エラー ビューアー ページ**  
  
 ESB 管理ポータルに表示される ESB エラー メッセージの処理のために送信されたときに、元のメッセージの値にエラーの結果があります。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]管理者またはユーザーは、失敗したメッセージを編集して、入り口処理のために送信するのには、「修復し、再送信」機能をサポートします。  
  
 含まれるメッセージが開かれ、1 つメッセージ表示 ページのビューで選択するメッセージの詳細、図 3 に示すようにします。 このビューでは、ユーザーがコンテンツや、メッセージのダウンロード をクリックして、メッセージを表示できます**編集**が修復し、メッセージを再送信、編集ビューに切り替えます。  
  
 ![メッセージ ビューアー ページ](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4 MessageViewerPage")  
  
 **図 3**  
  
 **エラーの詳細ビューを表示、ESB メッセージ ビューアー**  
  
 フォールト ビューアー、メッセージの再送信のプロセス一覧については、使用する手法など、ESB 管理ポータルの使用法のオプションの詳細と並べ替え、およびエラーの分析を参照してください[による BizTalk ESB の管理Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)します。