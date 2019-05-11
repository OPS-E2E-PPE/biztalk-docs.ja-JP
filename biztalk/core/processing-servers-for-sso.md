---
title: SSO の処理サーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2676de4e698f3ea9221b35c349819f163b74b3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255138"
---
# <a name="processing-servers-for-sso"></a>SSO の処理サーバー
複数コンピューター環境で、マスター シークレット サーバーと SSO データベースが作成した後をエンタープライズ シングル サインオン コンピューターにインストールできます以降。 これらは、通常、BizTalk Server または Host Integration Server のいずれかがインストールされているものコンピューターです。  
  
 最初のインストール プロセスは、最初のコンピューターと同じです。 ただし、構成は若干異なるなります。 マスター シークレット サーバーと SSO データベースは既に場所であるために選択**参加**構成ウィザードが表示されたら、**新しい SSO システムを作成する**または**既存システムに参加**.  
  
 SSO データベースがそのグループ用に構成されたデータベースを別のコンピューターに参加するには、1 台のコンピューターのグループの構成中にできるに注意してください。 これは可能ですが、これは推奨されません。  
  
## <a name="see-also"></a>参照  
 [以前のバージョンの SSO からのアップグレード](../core/upgrading-from-a-previous-version-of-sso.md)