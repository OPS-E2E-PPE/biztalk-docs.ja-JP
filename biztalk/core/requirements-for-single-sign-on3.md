---
title: TIBCO Rendevous アダプターの SSO の要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e61b456def74ee76d887fa42149ee95b9ca3cbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013739"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件

## <a name="prerequisites"></a>前提条件
シングル サインオン (SSO) を使用するために必要なものは次のとおりです。  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバー システム  
  
-   分離ホストは、信頼されている認証として構成する必要があります。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1. **トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。  
  
2. トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
   詳細については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications1.md)します。  
  
> [!NOTE]
>  作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
[Security](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)