---
title: 関連アプリケーションのプロパティを一覧表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5920263006a9188da83f82dcf65dad8fb8faada
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002723"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>関連アプリケーションのプロパティを一覧表示する方法
ここで示すコマンドを実行すると、関連アプリケーションに関する情報が表示されます。 関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)します。  
  
 SSO システムでは、関連アプリケーションのプロパティに関する情報は、関連アプリケーションの更新に使用する XML ファイルから取得します。 詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)します。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssomanage – displayapp *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>を表示する関連アプリケーションの名前を指定しますプロパティです。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*インストール ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssoclient – displayapp *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>を表示する関連アプリケーションの名前を指定しますプロパティです。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)