---
title: シングル サインオンの要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69bd8a232ba49f9e4ebb2eb3e53a70704bf0d80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240398"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するには、以下のソフトウェアがインストールされている必要があります。  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバー システム  
  
-   分離ホストとして構成する必要があります**信頼されている認証**します。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1. **トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。  
  
2. トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
   関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications4.md)します。  
  
> [!NOTE]
>  作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)