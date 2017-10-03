---
title: "従来シングル サインオン アプリケーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396ecfab477fe1ae17b1abbb09ebf71c9bcb58c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="traditional-single-sign-on-applications"></a>従来シングル サインオン アプリケーション
シングル サインオン (SSO) のプログラミング アーキテクチャには、アプリケーションとユーザー間でマップするためのマッピング コンポーネント、特定の用途の資格情報を参照するための参照コンポーネント、および管理タスクを実行するための管理コンポーネントが含まれています。 さらに、SSO にはアプリケーションがチケットを発行および引き換えるためのチケット インターフェイスも含まれています。  
  
## <a name="mapping"></a>マッピング  
 マッピングは、特定のユーザーを特定のアプリケーションにリンクするプロセスです。 関連アプリケーションと、`ISSOMapping`、`ISSOMapper`、および `ISSOMapper2` を使用しているユーザーの間をマップできます。 `ISSOMapping` では、マッピングの作成、削除、有効化、および無効化を行うことができます。 `ISSOMapper` および `ISSOMapper2` では、現在のユーザーのマッピング データの取得や設定を行うことができます。  
  
## <a name="lookup"></a>Lookup  
 シングル サインオンのプログラミング インターフェイスの中心となるのは、特定のユーザーの資格情報を参照する機能です。 `ISSOLookup1` および `ISSOLookup2` を使用して資格情報を参照できます。 `ISSOLookup1` では、独自の外部資格情報を取得できます。 これに対して `ISSOLookup2` では、ローカルの関連アプリケーションに関するリモート ユーザーの資格情報を参照できます。 前者は、従来のシングル サインオン アプリケーションに必要であり、後者は、ホスト側開始のシングル サインオン アプリケーションを記述するときに便利です。  
  
## <a name="administration"></a>管理  
 `ISSOAdmin`、`ISSOAdmin2`、および `ISSOConfigStore` を使用すると、管理機能の多くをプログラムで実行できます。 実行できるタスクは、シングル サインオンの構成や、シングル サインオンに対するアプリケーションの作成および記述です。 また、`ISSOConfigDB`、`ISSOConfigOM`、および `ISSOConfigSS` を使用して、SSO データベースを作成し、変更することもできます。 `ISSOPSAdmin` ではパスワード同期機能を管理できます。  
  
## <a name="communication-and-ticketing"></a>通信とチケット  
 アプリケーションでは、一般に、ユーザーがリモート アプリケーションと通信できるようにメッセージを発行します。 リモート アプリケーションとより安全に通信するには、シングル サインオン チケットを発行して引き換える必要があります。 発行し、チケットを引き換えるにプログラムによってもします。  
  
## <a name="see-also"></a>参照  
 [シングル サインオン アプリケーション](../core/single-sign-on-applications.md)