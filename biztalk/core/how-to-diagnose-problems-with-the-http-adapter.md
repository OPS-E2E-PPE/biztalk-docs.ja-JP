---
title: HTTP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91f818dd-11fa-4ea4-b904-e8e00b3e49b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110ae50f97d89b12b361a14caaac4f0df56989e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015723"
---
# <a name="how-to-diagnose-problems-with-the-http-adapter"></a>HTTP アダプターに関する問題の診断方法
ここでは HTTP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する  
  
- ソースまたはターゲットの IIS サーバー ログ ファイルには、HTTP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。 既定では、Windows Server の IIS ログ ファイルは、次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
### <a name="isolate-problems-with-the-http-send-adapter-by-posting-to-the-destination-url-with-a-client-that-uses-the-systemnethttpwebrequest-class"></a>System.Net.HttpWebRequest クラスを使用するクライアントを送信先 URL に POST して、HTTP 送信アダプターの問題を切り分ける  
  
1.  送信先 URL への POST を実行したときに HTTP 送信アダプターでエラーが生成される場合は、System.Net.HttpWebRequest クラスと HttpWebResponse クラスを使用するクライアントを作成して送信先 URL に POST します。 この方法は、問題が HTTP 送信アダプター限定のものであるか、送信先 URL への POST に関する一般的なものであるかを判断するのに役立ちます。  
  
2.  詳細については、System.Net.HttpWebRequest クラスおよび HttpWebResponse クラスを使用するクライアントを作成する方法を参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://go.microsoft.com/fwlink/?LinkId=66987)します。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [HTTP アダプターのトラブルシューティング](../core/troubleshooting-the-http-adapter.md)