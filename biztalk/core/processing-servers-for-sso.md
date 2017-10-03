---
title: "SSO の処理サーバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-servers-for-sso"></a>SSO の処理サーバー
複数コンピューター環境で、マスター シークレット サーバーと SSO データベースを作成した後にすることができますエンタープライズ シングル サインオン コンピューターにインストール以降。 このようなコンピューターは通常、BizTalk Server または Host Integration Server のどちらかがインストールされているコンピューターです。  
  
 最初のインストール プロセスは、1 台目のコンピューターと同じです。 ただし、構成は若干異なります。 マスター シークレット サーバーと SSO データベースが既に定められて、ので選択**参加**問い合わせるときに、構成ウィザード、**新しい SSO システムを作成**または**既存システムに参加**.  
  
 構成中に、あるコンピューター上のグループを、別のコンピューターの (そのグループ用に構成されていない) SSO データベースに参加させることも可能です。 ただし、これは可能であるというだけで、お勧めはできません。  
  
## <a name="see-also"></a>参照  
 [SSO の以前のバージョンからアップグレードします。](../core/upgrading-from-a-previous-version-of-sso.md)