---
title: シングル サインオンの要件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bc38cadb304f753a408c9c9573056c70b34671
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240308"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するには、次の必要があります。  
  
- BizTalk Server
  
- Visual Studio  
  
- エンタープライズ シングル サインオン  
  
- SSO をサポートするサーバー システム  
  
  分離ホストは、信頼されている認証として構成する必要があります。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1. **トランスポートのプロパティ**ウィンドウで、**はい**の**使用 SSO**。  
  
2. トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
   関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションを作成する](../core/creating-affiliate-applications2.md)します。  
  
> [!NOTE]
>  作業が完了したら、SSO を使用してへの任意の Web 共有フォルダーに戻してください**を共有しない**します。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [SSO プロジェクトの実行](../core/running-sso-projects1.md)   
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)