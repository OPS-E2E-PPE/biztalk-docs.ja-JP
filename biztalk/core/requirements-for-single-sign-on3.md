---
title: "TIBCO Rendevous アダプターの SSO の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40cf27a3b96534239fa871bd04b90febee9beafe
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件

## <a name="prerequisites"></a>前提条件
シングル サインオン (SSO) を使用するために必要なものは次のとおりです。  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバーのシステム  
  
-   分離ホストは、信頼されている認証として構成する必要があります。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
 詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications1.md)です。  
  
> [!NOTE]
>  作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
[セキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)