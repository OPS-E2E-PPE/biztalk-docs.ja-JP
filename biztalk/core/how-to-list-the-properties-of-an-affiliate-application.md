---
title: "関連アプリケーションのプロパティを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 651c629a0290fef9af20dce3771d87dbb9eeb82d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>関連アプリケーションのプロパティを一覧表示する方法
ここで示すコマンドを実行すると、関連アプリケーションに関する情報が表示されます。 関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。  
  
 SSO システムでは、関連アプリケーションのプロパティに関する情報は、関連アプリケーションの更新に使用する XML ファイルから取得します。 詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)です。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – displayapp *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連アプリケーションの名前を指定します。プロパティを表示するには。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブの取り付け*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssoclient – displayapp *\<アプリケーション名 >***ここで、 *\<アプリケーション名 >*関連アプリケーションの名前を指定します。プロパティを表示するには。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [関連アプリケーションの管理](../core/managing-affiliate-applications.md)