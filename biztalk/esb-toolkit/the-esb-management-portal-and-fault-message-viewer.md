---
title: ESB 管理ポータルおよびフォールト メッセージ ビューアー |Microsoft ドキュメント
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
ms.openlocfilehash: fb9a6e7272e7b707b6ba7650cfb93506c3a54a00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295210"
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a>ESB の管理ポータルおよびフォールト メッセージ ビューアー
主要なコンポーネント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]は Web ベース ポータルを提供する例外のさまざまな管理とアラートの通知機能ですさらに、有用な構成管理や Universal Description, Discovery, and Integration (機能。UDDI) 登録インターフェイスです。 図 1 は、現在実行中のアプリケーションの正常性の概要を説明すると、ポータルのホーム ページを示します。  
  
 ![ポータルのホーム ページ](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **図 1**  
  
 **ESB の管理ポータルのホーム ページ**  
  
 ユーザーは、図 2 に示すように、エラーのアンビエントと静的プロパティおよびエラー メッセージに含まれる元のメッセージの一覧を表示する、ESB の管理ポータルに表示されるエラー メッセージを選択できます。  
  
 ![[エラー ビューアー] ページ](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4 FaultViewerPage")  
  
 **図 2**  
  
 **ESB の管理ポータルの [ESB フォールト ビューアー] ページ**  
  
 ESB の管理ポータルに表示される ESB フォールト メッセージには、元のメッセージ処理のための送信時の値でのエラーの生じた可能性があります。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]管理者またはユーザーは、失敗したメッセージを編集して、入り口処理のために送信するには、「修復し、再実行してください」の機能をサポートします。  
  
 いずれかを選択含まれるメッセージが開かれ、メッセージの表示 ページのメッセージの詳細ビューで、図 3 に示すようにします。 コンテンツ、メッセージをダウンロード、またはをクリックして、メッセージを表示するこのビューで**編集**修復し、メッセージを再送信、編集ビューに切り替えます。  
  
 ![メッセージ ビューアー ページ](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4 MessageViewerPage")  
  
 **図 3**  
  
 **エラーの詳細ビューを表示、ESB メッセージ ビューアー**  
  
 フォールト ビューアー、メッセージの再送信プロセス、および一覧については、使用される手法を含む、ESB 管理ポータルの使用法のオプションの詳細と並べ替え、および、障害の分析について[BizTalk ESB によるの管理Toolkit](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)です。