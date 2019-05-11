---
title: アダプター プログラミングの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e5fef6c-6928-42e7-9a1f-42b5bd769937
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b407c6f0239798110b7b971ffa4febd58d6f70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361341"
---
# <a name="adapter-programming-configuration"></a>アダプター プログラミングの構成
パスワード同期アダプターのすべての種類には、用のアダプターをデザインするどのような非 Windows システムに応じて、別の構成要件があります。 関連アプリケーションと同様、一元的より安全に、構成プロパティを格納するのにエンタープライズ シングル サインオンの構成ストアを使用できます。  
  
 その他の構成ストアのアプリケーションを管理者は、検索し、アダプターの構成プロパティを記述する XML ファイルの読み取りをエンタープライズ シングル サインオンの管理のユーザー インターフェイスを使用できます。 管理ツールは、指定したアダプタの必要なプロパティの値を収集するためにプロパティ ページを表示するために、XML ファイルを使用します。 XML 名前/値の組み合わせと、構成ストアの間の読み込みと読み取りを ISSOConfigStore を使用することもできます。 または、SSOPS ツールを使用することができます。  
  
 アダプターを無効にする、エンタープライズ シングル サインオンの管理ツールを使用することもできます。 最初に作成、アダプターは無効です。  
  
## <a name="see-also"></a>参照  
 [パスワード同期アダプター](../core/password-sync-adapters.md)