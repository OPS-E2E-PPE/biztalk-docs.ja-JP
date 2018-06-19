---
title: 直接パスワード同期を使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6080589271d845432e875cb335a2ef354c9784ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255946"
---
# <a name="how-to-use-direct-password-sync"></a>直接パスワード同期を使用する方法
このバージョンのエンタープライズ シングル サインオンには、Windows から実行できる直接パスワード同期機能が実装されています。 この機能により、パスワード同期アダプタをバイパスし、SSO データベースのパスワードの更新を Windows から直接実行できます。  
  
 Windows からの直接パスワード同期は、次のような場合に役立ちます。  
  
-   エンタープライズ システムで Windows から Windows へのマッピングが必要な場合。  
  
-   Windows ユーザーのパスワードに変更が生じた場合は、SSO データベースにある外部ユーザーのパスワードを直接更新する必要があります。 パスワードの変更は、他のメカニズムを使用することにより、(外部ユーザーに対応する) バックエンド システム上で行うことができます。 たとえば、RACF 管理エージェントを使用した IBM メインフレーム上の Resource Access Control Facility (RACF) にあるパスワードを、Microsoft Identity Integration Server を使用して更新することが可能です。  
  
### <a name="to-enable-direct-password-sync"></a>直接パスワード同期を有効にするには  
  
1.  エンタープライズ シングル サインオンを開きます。  
  
2.  スコープ ペインで、をクリックして**関連アプリケーション**です。  
  
3.  適切なを右クリックして**関連アプリケーション**です。  
  
4.  **[プロパティ]** をクリックします。  
  
     **関連アプリケーションのプロパティ** ダイアログ ボックスが表示されます。  
  
5.  クリックして、**オプション**タブです。  
  
6.  選択、 **Windows から直接パスワード同期**チェック ボックスをオンします。  
  
7.  **[OK]** をクリックします。