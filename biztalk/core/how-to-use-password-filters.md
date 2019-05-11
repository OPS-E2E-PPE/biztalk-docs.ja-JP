---
title: フィルターするにはパスワードを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b7939c7a6e00404c9c1b4db586cc9723504aa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383354"
---
# <a name="how-to-use-password-filters"></a>パスワード フィルタを使用する方法
ENTSSO パスワード同期機能は、Microsoft Windows Active Directory と Windows 以外のシステム間でパスワードを同期します。 ただし、多くの外部システムでは、Active Directory で異なる場合は、パスワード ポリシーの要件があります。 (たとえば、IBM システムでは大文字に変換するパスワードが必要し、8 文字に制限されています)。これにより、「最小公分母」パスワード セキュリティに限って、2 つのシステムを使用する ENTSSO が強制されます。  
  
 ENTSSO パスワード フィルタ機能は、この制限に対処します。 パスワード フィルタは、定義されている追加のプロパティでパスワード同期アダプターだけです。 外部システムの条件を満たすように、パスワードをフィルタ処理をこれらの追加プロパティ (最大値または最小の長さの場合も、文字の制限など)。  
  
 パスワード フィルターを作成するときにその指定されている管理者グループが自動的に SSO 管理者アカウントとして使用することに注意してください。 SSO 管理者グループを変更する場合は、パスワード フィルターが新しい SSO 管理者アカウントを使用しても更新されるようにする必要があります。  
  
> [!NOTE]
>  、ENTSSO システムのすべての要素と同様は、パスワード フィルターは、機密性の高い情報が含まれてし、可能なユーザーの最小数を公開する必要があります。  
  
### <a name="to-create-a-password-filter"></a>パスワード フィルターを作成するには  
  
1.  **SSO 管理コンソール**を右クリックし、**パスワード管理**ノード、およびクリック**フィルターの作成**です。  
  
     **パスワード フィルタ ウィザード**が表示されます。  
  
2.  パスワード フィルターを作成するウィザードの指示に従います。  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a>パスワード フィルターを関連アプリケーションを割り当てる  
  
1.  適切なフィルターを右クリックし、をクリックし、**割り当てる**.  
  
2.  適切な選択**関連アプリケーション**します。