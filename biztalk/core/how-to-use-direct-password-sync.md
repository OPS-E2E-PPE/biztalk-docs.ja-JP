---
title: 直接パスワード同期を使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1334c2f-2020-46ea-a98c-f7688813e38c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9baa74b383ee30c1fba70c7f9bb966706d60142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333542"
---
# <a name="how-to-use-direct-password-sync"></a>直接パスワード同期を使用する方法
エンタープライズ シングル サインオンのこのバージョンには、Windows の機能から直接パスワード同期が含まれています。 これにより、パスワード同期アダプターをバイパスし、Windows から直接、SSO データベースのパスワードを更新することができます。  
  
 Windows から直接パスワード同期では、次の状況で役立ちます。  
  
-   エンタープライズ システムでは、Windows のマッピングに Windows が必要です。  
  
-   Windows ユーザーのパスワードの変更が発生したときに、SSO データベースで外部ユーザーのパスワードを直接更新する必要があります。 その他のメカニズムを使用して (つまり、外部ユーザーに対応します)、バック エンド システムのパスワードを変更できます。 たとえば、Microsoft Identity Integration Server を使用して、リソースへのアクセス管理機能 (RACF) RACF 管理エージェントを使用して、IBM メインフレームでパスワードを更新することができます。  
  
### <a name="to-enable-direct-password-sync"></a>直接パスワード同期を有効にするには  
  
1.  エンタープライズ シングル サインオンを開きます。  
  
2.  スコープ ペインで次のようにクリックします。**関連アプリケーション**します。  
  
3.  適切な右**関連アプリケーション**します。  
  
4.  **[プロパティ]** をクリックします。  
  
     **関連アプリケーションのプロパティ** ダイアログ ボックスが表示されます。  
  
5.  をクリックして、**オプション**タブ。  
  
6.  選択、 **Windows から直接パスワード同期**チェック ボックスをオンします。  
  
7.  **[OK]** をクリックします。