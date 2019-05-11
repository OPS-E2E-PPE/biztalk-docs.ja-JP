---
title: 従来のシングル サインオン アプリケーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ffc09f49e6fecc1d6773a3b5ea8e89f8d98ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313324"
---
# <a name="traditional-single-sign-on-applications"></a>従来のシングル サインオン アプリケーション
シングル サインオン (SSO) プログラミング アーキテクチャには、アプリケーションとユーザー、参照コンポーネントを指定した使用するための資格情報を参照および管理タスクを実行する管理コンポーネント間をマップするマッピング コンポーネントが含まれています。 さらに、アプリケーションを発行してチケットを引き換えるように SSO にはによってチケット インターフェイスも含まれます。  
  
## <a name="mapping"></a>マッピング  
 マッピングは、指定したアプリケーションが指定されたユーザーをリンクするプロセスです。 関連アプリケーションとを使用しているユーザーどうしをマップできる`ISSOMapping`、 `ISSOMapper`、および`ISSOMapper2`します。 `ISSOMapping`、作成、削除、有効にする、およびマッピングを無効にすることができます。 `ISSOMapper`、および`ISSOMapper2`を取得し、現在のユーザーのデータのマッピングを設定できます。  
  
## <a name="lookup"></a>Lookup  
 シングル サインオンのプログラミング インターフェイスのコアは、指定されたユーザーの資格情報を検索する機能です。 使用して資格情報を調べることができます`ISSOLookup1`、および`ISSOLookup2`します。 `ISSOLookup1`、、ユーザーが自身の外部資格情報を取得できるようにします。 これに対し、`ISSOLookup2`ローカルの関連アプリケーションに関するリモート ユーザーの資格情報を参照することもできます。 前者は従来のシングル サインオン アプリケーションに必要なのに対し、後者は便利なホスト側開始シングル サインオン アプリケーションを記述するとき。  
  
## <a name="administration"></a>管理  
 プログラムにより、管理機能の多くを行うことができます`ISSOAdmin`、 `ISSOAdmin2`、および`ISSOConfigStore`します。 このようなタスクには、シングル サインオンの構成の作成と、アプリケーションにシングル サインオンについて説明が含まれます。 作成して変更を使用して SSO データベース`ISSOConfigDB`、 `ISSOConfigOM`、および`ISSOConfigSS`します。 使用してパスワード同期機能を管理する最後に、`ISSOPSAdmin`します。  
  
## <a name="communication-and-ticketing"></a>通信とチケット  
 ユーザーがリモート アプリケーションと通信できるように多くの場合、アプリケーションがメッセージを発行します。 リモート アプリケーションをより安全に通信するには、は、発行し、シングル サインオン チケットを引き換える必要があります。 発行し、チケットを引き換えるにプログラムを使用できます。  
  
## <a name="see-also"></a>参照  
 [シングル サインオン アプリケーション](../core/single-sign-on-applications.md)