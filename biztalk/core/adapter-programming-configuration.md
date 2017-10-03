---
title: "アダプター プログラミングの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e908b3ac79970b917e1e7964868b3b9d5bd852d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-programming-configuration"></a>アダプター プログラミングの構成
パスワード同期アダプターは、その設計対象となるシステムによって構成の要件が異なります。 関連アプリケーションと同様、エンタープライズ シングル サインオンの構成ストアを使用することにより、構成プロパティを集中的かつより安全に保存できます。  
  
 管理者は、他の構成ストア アプリケーションと同じように、エンタープライズ シングル サインオンの管理ユーザー インターフェイスを使って、アダプターの構成プロパティが指定されている XML ファイルを検索し、読み込むことができます。 管理ツールは、プロパティ ページをレンダリングする際、XML ファイルを使って、指定されたアダプターで必要となるプロパティ値を収集します。 また、XML に格納されたプロパティ (名前/値ペア) は、ISSOConfigStore や SSOPS ツールを使用して構成ストアに保存したり、構成ストアから読み込んだりすることもできます。  
  
 エンタープライズ シングル サインオンの管理ツールを使用して、アダプターの有効と無効を切り替えることも可能です。 構成を最初に作成するとき、アダプターは無効になっています。  
  
## <a name="see-also"></a>参照  
 [パスワード同期アダプター](../core/password-sync-adapters.md)