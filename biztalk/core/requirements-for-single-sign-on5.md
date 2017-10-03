---
title: "シングル サインオン On5 の要件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], Single Sign-On
- SSO, requirements [JD Edwards OneWorld adapters]
- Single Sign-On, enabling [JD Edwards OneWorld adapters]
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b186eca2c24ef9c2731b66194a0543aba14e8bf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するのには、次が必要です。  
  
-   Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバー システム  
  
 分離ホストは、信頼されている認証として構成する必要があります。  
  
### <a name="to-enable-sso"></a>SSO を有効にするには  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
     関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。  
  
    > [!NOTE]
    >  作業を実行した後、SSO の使用に注意してくださいをリセットする**Web 共有**フォルダー**を共有しない**です。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on3.md)