---
title: 関連アプリケーションのプロパティを一覧表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250958"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a>関連アプリケーションのプロパティを一覧表示する方法
**Displayapp**コマンドは、関連アプリケーションに関する次の情報を示します。 関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)です。  
  
 シングル サインオン (SSO) システムでは、関連アプリケーションを更新するために使用する XML ファイルからこの情報を取得します。 詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../esso/how-to-update-the-properties-of-an-affiliate-application.md)です。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a>管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssomanage –displayapp <application name>`ここで、 *\<アプリケーション名 >* のプロパティを表示する関連アプリケーションの名前を指定します。  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a>クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには  
  
1.  をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。  
  
2.  コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。  
  
     既定のインストール ディレクトリは\<*ドライブの取り付け*>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型`ssoclient –displayapp <application name>`ここで、 *\<アプリケーション名 >* のプロパティを表示する関連アプリケーションの名前を指定します。  
  
## <a name="see-also"></a>参照  
 [ユーザー マッピングを管理します。](../esso/managing-user-mappings.md)   
 [関連アプリケーションの管理](../esso/managing-affiliate-applications.md)