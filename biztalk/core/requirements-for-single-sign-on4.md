---
title: TIBCO EMS アダプターの SSO の要件 |Microsoft ドキュメント
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
ms.openlocfilehash: 805d14e056da665f8828ce0244f28ed9adc40ff4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24012977"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) ではシングル サインオン (SSO) をサポートしています。 エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO EMS などのサーバー システムを表します。  
  
 シングル サインオンを使用するために必要なものは次のとおりです。  
  
-   Microsoft BizTalk Server
  
-   Visual Studio  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバーのシステム  
  
 分離ホストは、信頼されている認証として構成する必要があります。
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
     関連アプリケーションを作成する方法については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications5.md)です。  
  
    > [!NOTE]
    >  作業を実行した後、SSO を使用して任意の Web 共有フォルダーへのリセットに注意してください**を共有しない**です。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用するアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
[アダプターをセキュリティで保護します。](../core/security-in-biztalk-adapter-for-tibco-ems.md)