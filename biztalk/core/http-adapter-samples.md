---
title: HTTP アダプター サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: 6796ea39-2947-45df-b228-1ecdb23a7ab8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1747a9bb28bc84dc0f6772435411d07557bf463e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383109"
---
# <a name="http-adapter-samples"></a>HTTP アダプター サンプル
このセクションには、BizTalk HTTP アダプターを使用するときは、高度な機能を示すサンプルが含まれています。  
  
> [!NOTE]
>  このサンプルを実行する前に、次の手順を実行する必要があります。  
> 
> 1. IIS を開き、ISAPI および CGI の制限を追加します。  
> 
>    左側のパネルでコンピューター名をクリックし、右側のパネルし、追加、ISAPI または CGI パスに"ISAPI および CGI の制限 をクリックします。  
> 
>    64 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\BTSHTTPReceive.dll  
> 
>    32 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHTTPReceive.dll  
> 
>    許可された拡張パスを確認するかを実行します。  
>    2.  左側のパネルで HTTPRequestResponseSample をクリックし、中央のパネルで ハンドラー マッピング をクリックし、次の設定の"スクリプト マップの追加 をクリックします。  
> 
>    要求パス: btshttpreceive.dll  
> 
>    実行可能ファイル:  
> 
>    64 ビット コンピューターで次のように追加します。 C:\Program Files (x86)\Microsoft BizTalk Server \<version\>\HttpReceive64\  
> 
>    32 ビット コンピューターを追加します。 C:\Program Files (x86) \Microsoft BizTalk Server\<バージョン\>\HttpReceive\  
> 
>    要求の制限。  
> 
>    動詞:POST  
> 
>    アクセス:[スクリプト]  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [HTTPSolicitResponse](../core/httpsolicitresponse.md)  
  
-   [HTTPRequestResponse](../core/httprequestresponse.md)