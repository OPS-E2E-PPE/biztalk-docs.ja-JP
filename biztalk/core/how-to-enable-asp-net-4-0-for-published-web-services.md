---
title: 公開済み Web サービスを ASP.NET 4.0 を有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58646ff2-77a3-49dc-8593-f6e41d85d4f3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5613e22070b4103eb3744ebb8b7a0d008ca6df1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337973"
---
# <a name="how-to-enable-aspnet-40-for-published-web-services"></a>公開済み Web サービスの ASP.NET 4.0 を有効にする方法
IIS で ASP.Net のバージョンを設定します。

BizTalk Server Web サービス公開ウィザードは、.NET Framework に含まれているを ASP.NET で提供される機能に依存します。 ASP.Net のバージョンは、選択した .NET CLR バージョンに含まれています。 

このトピックでは、.NET CLR バージョンを変更する方法を示します。 

## <a name="prerequisites"></a>前提条件

IIS に含まれて、 **Web サーバー (IIS)** オペレーティング システムの役割です。 この役割をインストールするときにも、ASP.NET の新しいバージョンを選択します。 
  
## <a name="update-an-application-pool"></a>アプリケーション プールを更新します。
  
1.  開いている**インターネット インフォメーション サービス (IIS) マネージャー**:

    1. **サーバー マネージャー** **ツール**です。
    2. 選択**インターネット インフォメーション サービス (IIS) マネージャー**です。
  
2.  サーバー名を展開し、選択**アプリケーション プール**です。  
  
3.  アプリケーション プールを選択し、開く、**基本設定**です。  
  
4. 設定、 **.NET CLR バージョン**以降のバージョン、および選択を**OK**変更を保存します。  

> [!NOTE]
> Web.config ファイルのバージョンを変更することもできます。
 
## <a name="allow-the-aspnet-extension"></a>ASP.Net の拡張子を許可します。
  
1.  開いている**インターネット インフォメーション サービス (IIS) マネージャー**:

    1. **サーバー マネージャー** **ツール**です。
    2. 選択**インターネット インフォメーション サービス (IIS) マネージャー**です。
  
2.  サーバー名を選択し、ダブルクリック**ISAPI および CGI の制限**です。  
  
3. ASP.NET は確認**許可**32 ビットおよび 64 ビット バージョン。  
  
## <a name="see-also"></a>参照  
 [Web サービスを公開するための計画](../core/planning-for-publishing-web-services2.md)