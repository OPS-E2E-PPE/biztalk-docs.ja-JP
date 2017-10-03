---
title: "シングル サインオン On2 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling SSO
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c886792f36808152c4a27733544b09015c68f061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するのには、次の必要があります。  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバー システム  
  
 分離ホストは、信頼されている認証として構成する必要があります。  
  
### <a name="to-enable-sso"></a>SSO を有効にするには  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
 関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications2.md)です。  
  
> [!NOTE]
>  作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [SSO プロジェクトの実行](../core/running-sso-projects1.md)   
 [シングル サインオンを使用します。](../core/using-single-sign-on2.md)