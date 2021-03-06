---
title: シングル サインオンの要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03d043ef526957cd4590edc2a5d74396c1225a8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395282"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するには、が必要です。  
  
- Microsoft BizTalk Server 
  
- Visual Studio  
  
- エンタープライズ シングル サインオン  
  
- SSO をサポートするサーバー システム  
  
  分離ホストは、信頼されている認証として構成する必要があります。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
     関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications3.md)します。  
  
    > [!NOTE]
    >  作業が完了したら、SSO を使用していずれかに戻してください**Web 共有**フォルダー**を共有しない**します。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)