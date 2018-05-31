---
title: シングル サインオンの要件 |Microsoft ドキュメント
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
ms.openlocfilehash: fd2a1fb342911c904044c8099901c5056f17ac9f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013025"
---
# <a name="requirements-for-single-sign-on"></a>シングル サインオンの要件
シングル サインオン (SSO) を使用するのには、次が必要です。  
  
-   Microsoft BizTalk Server 
  
-   Visual Studio  
  
-   エンタープライズ シングル サインオン  
  
-   SSO をサポートするサーバー システム  
  
 分離ホストは、信頼されている認証として構成する必要があります。  
  
## <a name="enable-sso"></a>SSO を有効にします。  
  
1.  **トランスポートのプロパティ**ウィンドウで、**はい**の**SSO を使用する**です。  
  
2.  トランスポートのプロパティを指定するときに、適切な関連アプリケーションを選択します。  
  
     関連アプリケーションの作成方法の詳細については、次を参照してください。[関連アプリケーションの作成](../core/creating-affiliate-applications3.md)です。  
  
    > [!NOTE]
    >  作業を実行した後、SSO の使用に注意してくださいをリセットする**Web 共有**フォルダー**を共有しない**です。 フォルダーが共有されていると、そのフォルダーは使用中と見なされるので、フォルダーを使用しているアプリケーションが正しく更新またはアンインストールされません。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)