---
title: "フィルターするにはパスワードを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-password-filters"></a>パスワード フィルタを使用する方法
ENTSSO パスワード同期機能は、Microsoft Windows Active Directory と Windows 以外のシステムのパスワードを同期します。 しかし、多くの外部システムは、Active Directory とは異なるパスワード ポリシー要件を備えています (たとえば、IBM システムでは、パスワードは 8 文字以内の大文字で指定する必要があります)。このため、パスワード セキュリティに限って、ENTSSO では 2 つのシステム間の "最小限の共通要件" を使用します。  
  
 ENTSSO パスワード フィルタ機能は、この制限事項に対応しています。 パスワード フィルタは単なるパスワード同期アダプタで、いくつかのプロパティが追加で定義されています。 これらの付加的なプロパティ (最大長、最小長、大文字/小文字、文字制限など) により、外部システムの基準を満たすようにパスワードのフィルタ処理を実行します。  
  
 パスワード フィルターを作成するときに指定されている管理者グループに自動的としてを使用する SSO 管理者アカウントに注意してください。 SSO 管理者グループを変更すると、新しい SSO 管理者アカウントに応じてパスワード フィルタも更新されるようにする必要があります。  
  
> [!NOTE]
>  ENTSSO システムのすべての要素と同様に、パスワード フィルタには機密性の高い情報が含まれており、この情報を公開するのは必要最小限の担当者に抑えることが求められます。  
  
### <a name="to-create-a-password-filter"></a>パスワード フィルタを作成するには  
  
1.  **SSO 管理コンソール**を右クリックし、**パスワード管理**ノードをクリックして**フィルターの作成**です。  
  
     **パスワード フィルタ ウィザード**が表示されます。  
  
2.  ウィザードの指示に従って、パスワード フィルタを作成します。  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a>パスワード フィルタに関連アプリケーションを割り当てるには  
  
1.  適切なフィルターを右クリックし、をクリックして**割り当てる**しています.  
  
2.  適切な選択**関連アプリケーション**です。