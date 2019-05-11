---
title: TIBCO EMS アダプターの SSO の要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a07e4ecf344b06c9d1f98297acb3b3a851283e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399121"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) ではシングル サインオン (SSO) をサポートしています。 エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO EMS などのサーバー システムを表します。  
  
 シングル サインオンを使用するために必要なものは次のとおりです。  
  
- Microsoft BizTalk Server
  
- Visual Studio  
  
- エンタープライズ シングル サインオン  
  
- SSO をサポートするサーバー システム  
  
  分離ホストは、信頼されている認証として構成する必要があります。
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
     関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications5.md)します。  
  
    > [!NOTE]
    >  作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
[アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-tibco-ems.md)